### Mapping `cobra` IDs to HMDB ID's for fast lookup
_Aug 27, 2024_

In the process, that the _numbers in the_ HMDB ID's in the _spreadsheet_ were formatted to **7** digits, while those in the **`cobra.Model`** were to **5**, slapped me in the face.
Subsequently, I manually edited the entire spreadsheet file to `cobra`'s fixed width of __5__. It was no more than 17 rows anyways.

### Mid-wrangling crisis: a pleasant turn onto memory lane
_Aug 28, 2024_
Carrying on away with my plan from yesterday, I finally finished adding the __> half-missing__ `cobraID` column to the experimental data `DataFrame`. That even **uracil** could not be found in E. _coli_ Core metabolites was just too ludicrous for me.
Thus, I am deciding to sacrifice computational performance for the latest and greatest [iAF1260 E. _coli_ genome-scale metabolic model](http://bigg.ucsd.edu/models/iAF1260) from Palsson's "camp". Specifically, it'll be a > 580 $\times$ larger $S$ in terms of number of elements.

In querying the BiGG database portal for the first time, I learned that _their_ metabolites could be queried by _HMDB_ ID's, which are already in the original experimental data! Unfortunately failing to find the external database ID querying feature in BiGG's API, I accepted manually filling the BiGG ID's for the mere 13 rows with a HMDB ID, only to realize that "Ethanol" and "Ethanol 1" had the _same_ HMDB ID's, and "N-Carbamoylaspartate" "N-Carbamoylaspartate 1" likewise.

Besides their concentrations time series, their key differences lay in the `type` column. And so began my trip into memory lane, by H-NMR block. I am fairly certain that the differences between the entries of each pair are but laboratory artifacts of H-NMR spectroscopy which do not necessitate any particular or differential treatment in metabolic modelling. Therefore, I will merge them for "loading" into the concentrations vector $\vec{\mathbf{x}}$, discarding the H-NMR identification columns and summing the concentrations at each measurement time.

### E. _coli_ take up space
Had to write a function to split 🍴 each metabolite into those in extracellular space, `_e`, and those in cytosol, `_c`.

^ _Aug 30, 2024_
Actually, on second thought, FBA being _solely_ steady-state analysis, **only depends on metabolite concentrations when they deplete to less than the flux constraints draw**.
Thus, it is not so outrageous to have a run with **assuming that _all_ the amount of each metabolite measured are in the cytosol**, or in `cobra` terms in their `_c` state, from $t=0$.