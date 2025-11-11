2025-11-09 16:32

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 



_______
# PDL 5 - Experimenting (Ensembling)

**Ensembling:** creating multiple models and combining their predictions
- Simplest → build multiple models with different randomly initialized coefficients and then combine (`stack` in a tensor and then take mean over the sets of predictions)

*Note:* studies have shown that most datasets can be best modelled with either:
- Ensemble of decision trees (i.e. [[PDL 6 - Random Forests|random forest]], gradient boosting) → for structured data
	- Faster to train + easier to analyze → i.e. can determine which columns were most important
	- **Exceptions:** 
		- High cardinality categorical variables (many possible choices)
		- Columns contain data best understood by models (i.e. natural language)
- Multilayered NN using SDG → for unstructured data (audio, images, natural language)
	- Always superior for unstructured, even for structured


# References

