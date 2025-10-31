2025-10-30 15:20

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 


_______
# CV - PAPER Automated Powerlifting

**Dataset construction:** Used National Powerlifting Comp VODs from USA 2024
- Each lift got lights (need 2/3 white) and if fail → a flag
	- ![[Screenshot 2025-10-30 at 5.08.54 PM.png]] 
- Downsample → to get less processing
- PyTesseract → to find the lifter’s name and associated lights
- Figuring out when lift starts
	- Masked target frame + mean squared error (MSE) calculation on unmasked regions
- Flags → get with a KNN (k=3)
- MoveNet → feature extraction

___
**Comparison (Heuristics vs CNN):** 
- Heuristics → just track points and use rules
	- I.e. bar cannot move down
	- Must get depth
- CNN → similar enough input to a normal image 
	- Allows it to learn across time and joints
		- I.e. (3, f, k) is similar to (channels, height, width)
	- **Architecture:**
		- Conv → Max Pool → ReLU → Conv 2 → Linear → Output
	- **Input:** $K\in R^{N\times 3\times f\times k}$ 
		- N → number of videos
		- 3 → each keypoint has $(x,y,confidence)$ 
		- f → number of frames per video
		- k → number of keypoints per frame
	- **Output:** $F\in S^{3\times N}$ 
		- Returns 3 predictions (1 per judge)
			- Can be white, blue, red, yellow (0-3)
	- **Model:** 3 networks
		- Each one learns to predict one of the three judge flags (i.e. if the left side fails versus if the right side fails)
		- Because you don’t want to just give 3 reds every single time

# References
https://cs231n.stanford.edu/2024/papers/automating-powerlifting-judging-through-keypoint-detection.pdf?utm_source=chatgpt.com
