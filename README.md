Python script: ANOVA for seed traits using completely randomized design using two factor data
import pandas as pd
import statsmodels.api as sm
from statsmodels.formula.api import ols

df = pd.read_excel('seed_traits.xlsx')

model = ols('FGP ~ C(Genotype) * C(Treatment)', data=df).fit()
anova_table = sm.stats.anova_lm(model, typ=2)
print(anova_table)
