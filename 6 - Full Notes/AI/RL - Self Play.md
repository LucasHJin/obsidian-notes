2025-12-27 00:08

Status:


Tags:



_______
# RL - Self Play

*Note* → subcategory of [[RL - Multi Agent Reinforcement Learning (MARL)]] 

**Self-play:** training an agent by using former copies of itself (policy) as an opponent
- Bootstraps the opponent + progressively raises difficulty
	- Leads to improved policy
- Tradeoffs → Skill level vs generality of policy + stability
	- Training against same opponents for longer is more stable but may result in overfitting

**Elo:** provides relative skill level between 2 players in a zero sum game (reward is absolute)
- Zero sum game → one must win, one must lose (can’t have both win)
- Typically 1200 score baseline
- Steps:
	- Winning player takes the points
	- If it’s a tie → lower rated one takes points
	- Else points gained is dependent on who had higher elo
	- Compare who is expected to win with who actually won
		- ![[Screenshot 2025-12-27 at 12.13.48 AM.png|400]] 
		- ![[Screenshot 2025-12-27 at 12.15.06 AM.png|300]] 


# References

