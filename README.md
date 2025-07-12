# Conformal-Inference-for-Data-Integration-
This repository presents a methodological framework for constructing individual prediction intervals over a finite population using data obtained from both probability and non-probability samples. The core objective is to quantify predictive uncertainty when the available data sources differ in their sampling mechanisms and covariate distributions but are assumed to share a common data-generating process.

In this setup, we consider two different data sources from the same underlying population. The non-probability sample contains observations on both the response variable Y and the covariates X. Hpowever the selection mechanism for the non-proability is unknown and as a result using this data sourse solely for inferential purpose such as constructing prediction inetrvals could result in ambiguous inference about the population quantity. In contrast, the probability sample also contains values of Y and X, but is augmented with known inclusion probabilities, making it representative of the target population.

We start with an assumption that while the marginal distribution of the covariates may differ across the two samples, reflecting covariate shift, the conditional distribution of the response given the covariates, 
P(Y∣X), remains invariant across samples, as both are drawn from the same underlying finite population. We also assume transportability.

To construct valid prediction intervals in this setting, we adapt conformal inference techniques to accommodate covariate shift and unequal sampling designs. The predictive model is trained on the non-probability sample, leveraging its larger size and full response information. Calibration is then performed using the probability sample. For each calibration point, a conformity score is computed as a normalized residual. Instead of using equally weighted quantiles to define prediction intervals, we compute weighted quantiles of these conformity scores, where each score is weighted by the inverse of its inclusion probability. This reweighting accounts for the sampling design and enables the intervals to adjust appropriately for covariate shift.

Once calibrated, the method produces prediction intervals for each new observation from the population. These intervals are valid under minimal distributional assumptions and are tailored to the covariate distribution of the population. This framework enables distribution-free prediction interval construction in complex data integration settings, where uncertainty quantification is often difficult to achieve.

The proposed approach is particularly relevant to problems in survey statistics, small area estimation, and policy evaluation, where combining administrative, observational, and designed survey data is increasingly common but fraught with inferential challenges. By bridging ideas from conformal prediction and finite population inference, this work offers a rigorous and practical tool for data fusion with meaningful uncertainty guarantees.

REFERENCES: 
1) Tibshirani, R. J., Barber, R. F., Candes, E. J., and Ramdas, A. Conformal prediction under covariate shift, 2020.
2) Wieczorek, J. (2023). Design-based conformal prediction. Survey Methodology, Statistics Canada, Catalogue No. 12‑001‑X, Vol. 49, No. 2. Paper available at http://www.statcan.gc.ca/pub/12-001-x/2023002/article/00007-eng.htm.
