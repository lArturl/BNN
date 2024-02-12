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


### List of references

1. Merrifield, A. L., Brunner, L., Lorenz, R., Humphrey, V., & Knutti, R. (2023). Climate model Selection by Independence, Performance, and Spread (ClimSIPS v1.0.1) for regional applications. Geoscientific Model Development, 16, 4715–4747. https://doi.org/10.5194/gmd-16-4715-2023
2. Ban, N., Caillaud, C., Coppola, E. et al. The first multi-model ensemble of regional climate simulations at kilometer-scale resolution, part I: evaluation of precipitation. Clim Dyn 57, 275–302 (2021). https://doi.org/10.1007/s00382-021-05708-w
3. Powers JG, Klemp JB, Skamarock WC, Davis CA, Dudhia J, Gill DO, Coen JL, Gochis DJ, Ahmadov R, Peckham SE, Grell GA, Michalakes J, Trahan S, Benjamin SG, Alexander CR, Dimego GJ, Wang W, Schwartz CS, Romine GS, Liu Z, Snyder C, Chen F, Barlage MJ, Yu W, Duda MG (2017) The weather research and forecasting model: overview, system efforts, and future directions. Bull Am Meteor Soc 98(8):1717–1737. https://doi.org/10.1175/BAMS-D-15-00308.1
4. Giorgi F, Coppola E, Solmon F, Mariotti L, Sylla MB, Bi X, Elguindi1 N, Diro GT, Nair V, Giuliani G, Turuncoglu UU, Cozzini S, Güttler I, O’Brien TA, Tawfik AB, Shalaby A, Zakey AS, Steiner AL, Stordal F, Sloan LC, Brankovic C (2012) RegCM4: model description and preliminary tests over multiple CORDEX domains. Clim Res 52:7–29
5. Fumière Q, Déqué M, Nuissier O, Somot S, Alias A, Caillaud C, Laurantin O, Seity Y (2020) Extreme rainfall in Mediterranean France during the fall: added value of the CNRM-AROME convection-permitting regional climate model. Clim Dyn. https://doi.org/10.1007/s00382-019-04898-8
6. Pietikäinen JP, Markkanen T, Sieck K, Jacob D, Korhonen J, Räisänen P, Gao Y, Ahola J, Korhonen H, Laaksonen A, Kaurola J (2018) The regional climate model remo (v2015) coupled with the 1-D freshwater lake model FLake (v1): Fenno-scandinavian climate and lakes. Geosci Model Dev 11(4):1321–1342. https://doi.org/10.5194/gmd-11-1321-2018
7. Berthou S, Kendon EJ, Chan SC, Ban N, Leutwyler D, Schär C, Fosser G (2018) Pan-European climate at convection-permitting scale: a model intercomparison study. Clim Dyn. https://doi.org/10.1007/s00382-018-4114-6
8. Rockel B, Will A, Hense A (2008) The regional climate model COSMO-CLM (CCLM). Meteorol Z 17:347–348. https://doi.org/10.1127/0941-2948/2008/0309
9. T. Pearce, R. Tsuchida, M. Zaki, A. Brintrup, and A. Neely. Expressive priors in bayesian
neural networks: Kernel combinations and periodic functions. In Proceedings of the Thirty-fifth
Conference on Uncertainty in Artificial Intelligence, 2019. https://doi.org/10.48550/arXiv.1905.06076
10. Vitart, F., Robertson, A. W., Spring, A., Pinault, F., Roškar, R., Cao, W., ... & Zhou, S.: Outcomes of the WMO Prize Challenge to Improve Subseasonal to Seasonal Predictions Using Artificial Intelligence. Bulletin of the AmericanMeteorological Society, 103(12), E2878-E2886, 2022. https://doi.org/10.1175/BAMS-D-22-0046.1  https://github.com/crim-ca/crims2s
11. J. K. Meher and L. Das. Gridded data as a source of missing data replacement in station records.
Journal of Earth System Science, 128(3):58, 2019. https://doi.org/10.1007/s12040-019-1079-8
12. Zhe Sun, Alexander T. Archibald, Multi-stage ensemble-learning-based model fusion for surface ozone simulations: A focus on CMIP6 models, Environmental Science and Ecotechnology, Volume 8, 2021, 100124, ISSN 2666-4984, https://doi.org/10.1016/j.ese.2021.100124.
13. Smith, K. L., & Stenke, A. (2020). Bayesian Neural Network Ensembles for Total Column Ozone Retrieval. arXiv preprint arXiv:2010.03561. Retrieved from https://doi.org/10.48550/arXiv.2010.03561
14. A. Kustiyo, A. Buono, A. Faqih and K. Priandana, "Analysis on Dimensionality Reduction Techniques for Sub-Seasonal to Seasonal Rainfall Prediction," 2021 International Conference on Computer System, Information Technology, and Electrical Engineering (COSITE), Banda Aceh, Indonesia, 2021, pp. 156-160, doi: 10.1109/COSITE52651.2021.9649588.
15. Hammami, D., T. S. Lee, T. B. M. J. Ouarda, and J. Lee (2012), Predictor selection for downscaling GCM data with LASSO, J. Geophys. Res., 117, D17116, doi:10.1029/2012JD017864.
16. Sengupta, U., Amos, M., Hosking, J. S., Rasmussen, C. E., Juniper, M., & Young, P. J. (2020). Ensembling geophysical models with Bayesian Neural Networks. In Advances in Neural Information Processing Systems (NeurIPS) 2020. arXiv:2010.03561 [physics.geo-ph]. https://doi.org/10.48550/arXiv.2010.03561
17. Hans Hersbach, Bill Bell, Paul Berrisford, Shoji Hirahara, András Horányi, Joaquín Muñoz-Sabater, Julien Nicolas, Carole Peubey, Raluca Radu, Dinand Schepers, Adrian Simmons, Cornel Soci, Saleh Abdalla, Xavier Abellan, Gianpaolo Balsamo, Peter Bechtold, Gionata Biavati, Jean Bidlot, Massimo Bonavita, Giovanna De Chiara, Per Dahlgren, Dick Dee, Michail Diamantakis, Rossana Dragani, Johannes Flemming, Richard Forbes, Manuel Fuentes, Alan Geer, Leo Haimberger, Sean Healy, Robin J. Hogan, Elías Hólm, Marta Janisková, Sarah Keeley, Patrick Laloyaux, Philippe Lopez, Cristina Lupu, Gabor Radnoti, Patricia de Rosnay, Iryna Rozum, Freja 
Vamborg, Sebastien Villaume, Jean-Noël Thépaut. (2020). The ERA5 global reanalysis. Quarterly Journal of the Royal Meteorological Society. https://doi.org/10.1002/qj.3803
18. Knutti, R., Rugenstein, M. & Hegerl, G. Beyond equilibrium climate sensitivity. Nature Geosci 10, 727–736 (2017). https://doi.org/10.1038/ngeo3017
19. Merrifield, A. L., Brunner, L., Lorenz, R., Medhaug, I., & Knutti, R. (2020). An investigation of weighting schemes suitable for incorporating large ensembles into multi-model ensembles. Earth System Dynamics, 11(3), 807–834. https://doi.org/10.5194/esd-11-807-2020 
20. Zammit-Mangion, A., Kaminski, M. D., Tran, B.-H., Filippone, M., & Cressie, N. (2023). Spatial Bayesian Neural Networks. arXiv preprint arXiv:2311.09491. Retrieved from https://doi-org.uaccess.univie.ac.at/10.48550/arXiv.2311.09491 
21. Sharma, H., Jennings, E. Bayesian neural networks at scale: a performance analysis and pruning study. J Supercomput 77, 3811–3839 (2021). https://doi.org/10.1007/s11227-020-03401-z
