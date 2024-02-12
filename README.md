# BNN


## Questions

- How to reduce computational cost, while leaving maximal accuracy in predictions
    Example with GraphCast
- How effective is prunning for the complexity reduction  
- How effective are dimensionality reduction techniques 
    (PCA, wavelet decomposition, singular value decomposition.)
- How much do attention layers contribute to accuracy 



## Meeting log

### Meeting_1 03.04.2023

- 5 (max. 10) GCM or RCM models to mix. I will ask my colleagues tomorrow which kind of models we should use. They have a bit more knowledge on climate scenarios.
- temperature and precipitation as main parameters (target) and if it makes sense we also add additional features (topography, pressure, etc. based in literature too)
- target/ground truth is ERA5. Please find attached a script for downloading ERA5 (only temperature but parameters can easily be added). I set the retrieval period to 2010-2022, so that we could use e.g. 2010-2020 as training, 2021 as validation, and 2022 as sort of test year. You need to have an Copernicus account: https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-single-levels
- Domain/target region will be Central Europe, maybe something like upper left = -10,65 and lower right = 35,40. In case this is too big we still can reduce it. This is not yet set to that domain in the script.


### Meeting_2 17.02.2023

Main goals so far:
- Scetch possible questions of research
- provide GitHub
- write progress into Overleaf

Overall conversation: 

Attention layers are probably cheaper then investing a lot of time into feature engineering.

Example: Paper about forecasting random forest and neural network, how it compares to multilinear regression if feature engeneering and adding non-linear terms, how much effect it has, showed that using nonlinear features nearly as good as other methods.

Attention layers provide max of 5 parameters/features compared to feature engineering, that provides a lot of new data.
Benchmark method will be comparing our model to classical weight mixing of models. 
Possible question: How does it compare to BNN without attention layers.
Question to decide: if mean prediction or outliers are of importance.
20-100 realization of models combined by mean weightning scheme (other methods possible if makes sense).

How can we ensure that we get best of the best for each parameter, avoiding smoothing out things that are important. Not leaning towards minimum requirement for combining models, like mean weighting. 