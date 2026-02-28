This project aims to study the correlation between ISOs energy prices in USA and Canada and use them to help make estimates on wheat prices.

The logic:
Both ISOs and commodities, similar to wheat share multiple variables; principally weather forecasts, to infer future prices. Weather forecast data is expensive. Can we take advantage of free-to-use data that (such as expected pool prices) to make inferences on other markets, without having to pay loads of money?

Stage 1 work - EDA:
Can we observe enough correlation between weather related comodity prices and energy-price forecasts to warrant developping and ML pipeline?
- Identify major ISOs that provide extensive info via API for free (like AESO)
    - Research and note the weights of renewable energies (more renewable = more weight on local prices)
- Research and identify a good source for historic energy prices. Identify multiple for parallel downloading (multiple batches across APIs)
- Develop straightforward EDA visuals to identify potential patterns.
- Consider multiple techniques- research if stuff like PCA would make sense - how do we deconstruct price forecasts?

Stage 2 workd - Develop benchmarks and basic pipeline
- Research and fetch benchmark forecasts for identified commodities
- Develop an ML pipeline (fetch/clean/transform/split/train/validate)
- Compare results to benchmarks (reality/bench-forecast/infered-forecast)
- Research and introduce commodity specific variables to improve the above

Stage 3- Inference Pipeline on successful implementation of the above
- If the above seems fruitful:
    - Recreate entirely separate pipeline to run in prod
    - Run in paper environment for 2 weeks and fix bugs/edge cases.



Infrastructure:

- Stage 1:
    - Environment: local
    - Tools: 
        - Notebook
        - Pyplot
    - Libraries:
        - if ISO  have libraries, else standard get requests to their APIS
- Stage 2:
    - Environment: local to start -> AWS 
    - Tools: python repo, postgres
    - Libraries: tbc after stage 1
- Stage 3:
    - Environment: local for paper -> AWS prod
    - Tools: tbc
    - Libraries: tbc
