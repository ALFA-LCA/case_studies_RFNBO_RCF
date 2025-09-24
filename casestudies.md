# H1: Co-products

-   How to allocate emissions to oxygen

-   How to calculate the share of RFNBO with emissions from auxiliaries

![](../images/h1_allocation.svg)

Fully renewable electricity is attributed zero GHG emissions. Therefore, the only emissions come from auxiliaries.

??? info "Auxiliaries"
    Auxiliary inputs are all inputs not contributing to the heating value of the RFNBO. In the case of water electrolysis, this might be water supply and treatment, heat and other similar input.

    To simplify the example, we grouped all of them together and displayed the impact directly related to the energy in the RFNBO output.

Emissions can be allocated to the co-products by the economic value (according to point 15(f), because oxygen has no energy content).

## Assumptions

The main assumption is that the oxygen is valorized (sold) as a product. For electrolysers where the oxygen has no economic value, no emissions can be allocated to it.

We assume that auxiliaries are run on grid electricity. It would of course be possible to use renewable electricity for them too.

| Parameter                   |    Symbol          | Example value           |
|----------------------------|:--------------:|:------------------------:|
| Efficiency of the electrolyser | $\eta_{ely}$ | $60\color{grey}{\%}$ |
| Grid electricity for auxiliaries | $el_{grid\_aux}$ | $0.05\ \color{grey}{\left.MJ_{el}\middle/MJ_{hydrogen}\right.}$       |
| Economic value of RFNBO hydrogen | $v_{hydrogen}$  | $6\ \color{grey}{\left.\unicode{x20AC}\middle/{kg}_{hydrogen}\right.}$   |
| Economic value of oxygen | $v_{oxygen}$ | $0.3\ \color{grey}{\left.\unicode{x20AC}\middle/{kg}_{oxygen}\right.}$  |
| Ratio (mass) of produced oxygen per of hydrogen | $r_{oh}$ | $4\ \color{grey}{\left.{kg}_{oxygen}\middle/{kg}_{hydrogen}\right.}$ |
| Fully renewable electricity GHG intensity | $CI_{ren}$ | $0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{el}\right.}$ |
| Grid GHG intensity | $CI_{grid}$                  | $50\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{el}\right.}$  |

## Calculation

Emissions attributed to all products: 

$$
\begin{aligned}
{E}_{products} &= \left(e_{i,elastic} + e_{i,rigid} - e_{ex-use}\right) + e_p + e_{td} + e_u - e_{ccs}
\\
e_{i,rigid},\ e_{ex-use},\ e_{td},\ e_u,\ e_{ccs} &&= 0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\\
e_{i,elastic} &= CI_{ren} \times \eta_{ely} &= 0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\\
e_p &= {CI}_{grid} \times el_{grid\_aux} &= 2.5\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\\
E_{products} &&=  2.5\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\end{aligned}
$$

Emissions attributed to hydrogen:

$$
E_{hydrogen} = E_{products} \times \frac{v_{hydrogen}}{v_{hydrogen} + v_{oxygen} \times r_{oh}} = 2.1\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
$$

??? success "Threshold reached"
    The threshold of $28.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}$ is met. We can declare the fuel as RFNBO (or low carbon fuel).

Share of RFNBO in the output: $Share_{RFNBO-H_2} = 100\color{grey}{\%}$

## Conclusion

This case study shows that the share of RFNBO is calculated on the energy share of relevant inputs, while emissions are calculated based on all emissions, including auxiliaries. The emissions can be attributed to co-products, in case of products without energy content, economic allocation is used.

# H2: Time averaging

-   How to average over different timeframes

![](../images/h2_grid.svg)

Electrolyser running at 27.8 MW (100 GJ/h) with fully renewable, directly connected electricity, complemented by grid electricity. Oxygen is vented.

This case study shows that until 2030, it is possible to choose between monthly averaging or hourly averaging. As an example, we show an example of both. We pick one hour with particularly low renewables to exemplify how the calculation has to be done.

## Assumptions

| Parameter                   |    Symbol          | Monthly averaging                | Hourly averaging, low renewables |
|----------------------------|--------------|:----------------:|:---------------:|
| Efficiency of the electrolyser | $\eta_{ely}$        | $60\color{grey}{\%}$                         {: colspan=2} |
| Relevant renewable electricity used | $el_{ren}$     | $60\ \color{grey}{TJ}$                     | $40\ \color{grey}{GJ}$     |
| Relevant grid electricity used | $el_{grid\_ely}$ | $12\ \color{grey}{TJ}$                      | $60\ \color{grey}{GJ}$     |
| Grid electricity for auxiliaries | $el_{grid\_aux}$ | $3.6\ \color{grey}{TJ}$                     | $5\ \color{grey}{GJ}$     |
| Fully renewable electricity GHG intensity | $CI_{ren}$ | $0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{el}\right.}$ {: colspan=2} |
| Grid GHG intensity | $CI_{grid}$                  | $50\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{el}\right.}$  {: colspan=2} |

## Calculation

### Hourly averaging, low renewables

Amount of hydrogen produced: 

$$
{prod}_{H2} = \left(el_{ren} + {el}_{grid\_ely} \right)  \times  \eta_{ely} \approx 60\ \color{grey}{GJ}
$$

Total GHG intensity:

$$
\begin{aligned}
{E}_{H_2} &= (e_{i,elastic} + e_{i,rigid} - e_{ex-use}) + e_p + e_{td} + e_u - e_{ccs}
\\
e_{i,rigid},\ e_{ex-use},\ e_{td},\ e_u,\ e_{ccs} &&= 0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\\
e_{i,elastic} &= \frac{{el}_{grid\_ely}  \times  CI_{grid}}{{prod}_{H2}} &\approx 50\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\\
e_p &= \frac{el_{grid\_aux} \times  CI_{grid}}{{prod}_{H2}} &\approx 4.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\\
{E}_{H2} &&\approx 54.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\end{aligned}
$$

??? failure "Threshold not reached"
    The threshold of $28.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}$ is not met. We cannot declare the fuel as RFNBO (or low carbon fuel).

Share of RFNBO in the output: $Share_{RFNBO-H_2} = 0\color{grey}{\%}$ because threshold is not met. The whole fuel output cannot be declared as RFNBO or low-carbon fuel.

??? tip "Hour with high renewables"
    This example should not imply that hourly averaging is bad. In other hours, the share of renewables is higher than the average, and a higher share of the production can be declared as RFNBO. In many cases, monthly averaging might not reach the threshold, and the whole monthly production could not be declared as RFNBO.

### Monthly averaging

Amount of hydrogen produced:

$$
{prod}_{H2} = \left(el_{ren} + {el}_{grid\_ely} \right)  \times  \eta_{ely} \approx 43.2\ \color{grey}{TJ}
$$

Total GHG intensity:

$$
{E}_{H2} = \frac{\left( {el}_{grid\_ ely} + el_{grid\_aux} \right)  \times  CI_{grid}}{{prod}_{H2}} \approx 18.1\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
$$

??? success "Threshold reached"
    The threshold of $28.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}$ is met. We can declare the fuel as RFNBO (or low carbon fuel).

Share of RFNBO in the output: 

$$
Share_{RFNBO-H_2} = \frac{el_{ren}}{el_{ren} + {el}_{grid\_ely}} \approx 83\color{grey}{\%}
$$

The remainder is low-carbon fuel.

## Conclusion

This case study shows how averaging over shorter time scales can exclude some periods with low renewables from the RFNBO production. In other cases that are not shown here, the contrary could happen that the average over a longer period has a too high GHG intensity to qualify.

# H3: Hydrogen full example

-   System boundaries
-   Where to find more information

![](../images/h3_hydrogen.svg)


??? "Renewable electricity production"
    ## Renewable electricity production
    
    ### Requirements to qualify as renewable
    
    -   **Direct connection** if renewable production generating installation came into operation not earlier than 36 months before the installation producing renewable liquid and gaseous transport fuel of non-biological origin [ADD.3](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_3) [Q12](../FAQ/faq.md#Q12) [Q13](../FAQ/faq.md#Q13) [Q14](../FAQ/faq.md#Q14) 
    
    -   In a **bidding zone** where the average proportion of **renewable electricity exceeded 90%** in the previous calendar year (and for the five following years). Limited to $\text{full load hours} < 8760\;h  \times \text{RES-E share}$ [ADD.4](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_4) [Q15](../FAQ/faq.md#Q15) [Q16](../FAQ/faq.md#Q16) [Q17](../FAQ/faq.md#Q17) 
    
    -   In a **bidding zone** where the **emission intensity of electricity is lower than** $18\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{el}\right.}$  with renewable PPAs and temporal and geographical correlation [ADD.4](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_4)
    
    -   During **imbalance settlement period** [ADD.4](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_4) [Q18](../FAQ/faq.md#Q18) 
    
    -   If additionality, temporal correlation and geographical correlation are met [ADD.5](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_5) [ADD.6](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_6) [ADD.7](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_7) [Q19](../FAQ/faq.md#Q19) [Q20](../FAQ/faq.md#Q20) [Q21](../FAQ/faq.md#Q21)  [Q22](../FAQ/faq.md#Q22) [Q23](../FAQ/faq.md#Q23) [Q24](../FAQ/faq.md#Q24) [Q25](../FAQ/faq.md#Q25) [Q26](../FAQ/faq.md#Q26) [Q27](../FAQ/faq.md#Q27) [Q28](../FAQ/faq.md#Q28) [Q29](../FAQ/faq.md#Q29) 
    
    ### Combination of options
    
    -   All sourcing options can be combined, but if electricity is used in a time period that does not qualify as renewable, a share of the output equal to this electricity share in the inputs will not be an RFNBO. [Q30](../FAQ/faq.md#Q30) 
    
    ### What electricity inputs are considered
    
    -   To define the share of RFNBO produced, the share of electricity that counts as renewable in all relevant inputs is considered. Relevant inputs are inputs contributing to the energy content of the fuel. [GHG.3](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q59](../FAQ/faq.md#Q59) [Q60](../FAQ/faq.md#Q60) [Q65](../FAQ/faq.md#Q65) [Q66](../FAQ/faq.md#Q66) 
    
    ### Temporal aspects
    
    -   Temporal correlation of renewable electricity production and RFNBO production is necessary if they are not connected through a direct connection.
    
    -   The time period over which a “batch” of fuel (with the same GHG intensity) is produced can be up to one month, but needs to be in line with the requirements applying for temporal correlation. [GHG.1](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q65](../FAQ/faq.md#Q65) 
    
    ### Geographical aspects
    
    -   Geographical correlation of renewable electricity production and RFNBO production is necessary if they are not connected through a direct connection.
    
    -   Geographical correlation is given if electricity producer and electrolyser are in the same bidding zone, or in an interconnected bidding zone while the electricity price in the zone with the electrolyser is lower than in the interconnected bidding zone, or the renewable energy is produced in an interconnected offshore bidding zone. [ADD.7](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_7)
    
    ### Example in this case study
    
    Renewable electricity is sourced in the third country via a direct connection and a PPA with additionality, temporal and geographical correlation are met. The relevant time period considered is one month.

    | Parameter                   |    Symbol          | Example value |
    |----------------------------|:--------------:|:-----------------------:|
    |Total GHG intensity | $CI_{ren}$ | $0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{el}\right.}$ |
        
    
    
??? "Grid electricity"
    ## Grid electricity
    
    ### Grid electricity used in electrolyser
    
    -   If grid electricity is used in the same time period as renewable electricity, the output contains a share of RFNBO and a share of (low-carbon) fuel proportional to the energy input. [GHG.3](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1)
    
    -   The GHG intensity of grid electricity can be calculated using the methodology in [C](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#d1e825-23-1)
    
    ### Auxiliaries powered by grid electricity
    
    Auxiliaries can be powered by grid electricity. The emission intensity of this electricity has to be taken into account, but the share of RFNBO in the output is not affected. [GHG.3](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q11](../FAQ/faq.md#Q11) 
    
    ### Example in this case study
    
    | Parameter                   |    Symbol          | Example value |
    |----------------------------|:--------------:|:-----------------------:|
    |Total GHG intensity | $CI_{grid}$ | $100\ \color{grey}{\left.g\,CO_2\,eq\middle/kWh_{el}\right.}$ |
        
??? "Water desalination"
    ## Water desalination
    
    ### System boundaries, relevant inputs
    
    As the energy used to desalinate seawater is not adding to the heating value, it is not considered a "relevant input". So it doesn't change the content of RFNBO in the final fuel.

    But it has to be taken into account to calculate the GHG emissions.
    
    ### Example in this case study

    To simplify, it is considered that only fully renewable electricity is used in the process, so there are no GHG emissions.

    
??? "Electrolysis"
    ## Electrolysis
    
    ### Share of RFNBO
    
    The share of RFNBO is calculated for each processing step based on the share of the relevant energy inputs. [GHG.8](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1)
    
    ### GHG intensity
    
    -   All fuel outputs have the same GHG intensity [GHG.1](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q53](../FAQ/faq.md#Q53) 
    
    -   The GHG intensity is calculated by dividing all emissions by the overall energy in the fuel. [GHG.1](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1)
    
    ### Example in this case study
    
    The relevant time period considered is one month.
    
    | Parameter                   |    Symbol          | Example value |
    |----------------------------|:--------------:|:-----------------------:|
    |Relevant renewable electricity used | $el_{ren}$ | $500\ \color{grey}{GWh}$ |
    |Relevant grid electricity used | $el_{grid\_ely}$ | $50\ \color{grey}{GWh}$ |
    |Grid electricity for auxiliaries | $el_{grid\_aux}$ | $0.5\ \color{grey}{GWh}$ |
    |Efficiency of the electrolyser | $\eta_{ely}$ | $60\color{grey}{\%}$ |
    
    Total GHG intensity: 
    
    $${CI}_{H2} = \frac{\left( {el}_{grid\_ely} + el_{grid\_aux} \right) \times CI_{grid}}{\left( el_{ren} + {el}_{grid\_ely} \right) \times \eta_{ely}} \approx 4.3\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ\right.}$$
    
    Share of RFNBO in the output:  $Share_{RFNBO-H2}  \frac{el_{ren}}{el_{ren} + {el}_{grid\_ely}} \approx 91\%$
    
??? "Oxygen as a co-product"
    ## Oxygen as a co-product
    
    ### Allocation for products with no energy content
    
    Emissions can be allocated to the co-products by the economic value (because oxygen has no energy content) [GHG.15(f)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1).

    For details on the calculation, see [Co-products case study](#h1-co-products)
    
    ### Example in this case study

    To simplify, it is considered that oxygen is not sold.

# R1: Relevant inputs

-   How to determine if an energy input is “relevant”

![](../images/r1_ammonia_relevant energy_plain.svg)

Cracking Ammonia is endothermic, the heat can be supplied externally or by burning part of the ammonia. Here we assume that the energy is supplied electrically.

## Assumptions

??? tip "Transports"
    For this example, the transport process has been oversimplified. In reality, emissions caused by the transport need to be taken into account. This includes emissions from the ship, charging, uncharging and all other intermediate processes, including upstream emissions of the energy inputs.

| Parameter                   |    Symbol          | Example value |
|----------------------------|:--------------:|:---------------------:|
|Hydrogen demand Haber process (ammonia production) | ${hydrogen}_{input}$ | $1.16\ \color{grey}{\left.MJ_{H_2}\middle/MJ_{{NH}_3}\right.}$ |
|Ammonia demand for cracking | ${ammonia}_{input}$ | $0.88\ \color{grey}{\left.MJ_{{NH}_3}\middle/MJ_{H_2}\right.}$ |
|Electricity demand Haber process | $el_{grid\_Haber}$ | $0.75\ \color{grey}{\left.MJ_{el}\middle/MJ_{{NH}_3}\right.}$ |
|Heat demand, cracking process | $heat_{cracking}$ | $0.05\ \color{grey}{\left.MJ\middle/MJ_{H_2}\right.}$ |
|Heat efficiency | $\eta_{heat}$ | $95\ \color{grey}{\%}$ |
|Hydrogen GHG intensity | $CI_{H_2}$ | $0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{H_2}\right.}$ |
|Grid GHG intensity | $CI_{grid}$ | $25\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{el}\right.}$ |

As the output energy of the cracking process (1 MJ hydrogen) is bigger than the ammonia input (0.88 MJ), all the electricity used in the cracking process needs to be considered as a relevant input.

## Calculation

Total GHG intensity:

$$
\begin{aligned}
{E}_{H_2} &= (e_{i,elastic} + e_{i,rigid} - e_{ex-use}) + e_p + e_{td} + e_u - e_{ccs}
\\
e_{i,rigid},\ e_{ex-use},\ e_p,\ e_{td},\ e_u,\ e_{ccs} &&= 0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\\
e_{i,elastic,ammonia} &= {ammonia}_{input} \times \left(el_{grid\_Haber}  \times CI_{grid} + {hydrogen}_{input} \times CI_{H_2} \right) &\approx 16.5\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\\
e_{i,elastic,heat} &= \frac{heat_{cracking} \times CI_{grid}}{\eta_{heat}} &\approx 1.3\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\\
{E}_{H_2} &= e_{i,elastic,ammonia} + e_{i,elastic,heat} &\approx 17.8\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\end{aligned}
$$

??? success "Threshold reached"
    The threshold of $28.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}$ is met. We can declare the fuel as RFNBO (or low carbon fuel).


Share of RFNBO in the output is 

$$
Share_{RFNBO-H_{2}} = \frac{{ammonia}_{input}}{{ammonia}_{input} + heat_{cracking}} \approx 95\color{grey}{\%}
$$

The remainder is low-carbon fuel.

## Conclusion

This case study shows that some transport processes that need energy to split the transported product at destination might need to consider the energy needed for the split as relevant energy. If this energy is not fully renewable, the share of RFNBO will decrease.

One way to increase RFNBO share and lower the emissions is to use a part of the RFNBO ammonia to power the cracking process.

# R2: Integrated processes

-   How to count different integrated processes together

![](../images/r2_integrated rWGS and FT.svg)

Hydrogen production as in [case study 2](H2-Time-averaging.md), shift with CO~2~ and subsequent Fischer Tropsch synthesis to kerosene, assuming only kerosene as output to simplify the example.

The shift reaction and Fischer Tropsch can be either seen as an integrated process, or as two separate processes. There could be differences in calcluating the share of RFNBO if when looking at them as seperate processes, on process increases the heating value, and thus the heating energy needs to be accounted as a relevant input.

According to the Q&A, the shift reaction and FT reaction should be considered as an integrated process.

## Assumptions

| Parameter                   |    Symbol          | Example value |
|----------------------------|:--------------:|:---------------------:|
|Amount of RFNBO hydrogen | ${prod}_{RFNBO-H_2}$ | $300\ \color{grey}{GJ}$ |
|Amount of LC hydrogen | ${prod}_{LC-H_2}$ | $30\ \color{grey}{GJ}$ |
|Hydrogen GHG intensity | ${CI}_{H2}$ | $14\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}$ |
|Relevant grid electricity used for the shift reaction | $el_{grid\_shift}$ | $80\ \color{grey}{GJ}$ |
|Share of the (electric) heat energy ending up in the syngas | $Share_{heat\_to\_heating\_value}$ | $10\color{grey}{\%}$ |
|Efficiency of the shift reaction | $\eta_{shift}$ | $99\color{grey}{\%}$ |
|Shift reaction grid GHG intensity | $CI_{grid\_shift}$ | $5\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{el}\right.}$ |
|Efficiency of the FT reaction | $\eta_{FT}$ | $70\color{grey}{\%}$ |

## Calculation

Energy coming out of the FT reaction: 
$${En}_{output} = \left({prod}_{H2} \times \eta_{shift} + el_{grid\_shift} \times Share_{heat\_to\_heating\_value} \right)  \times  \eta_{FT} = 234.3\ \color{grey}{GWh}
$$

This is lower than the hydrogen input, so the electricity does not have to be considered a relevant input.

Total GHG intensity: 

$$
{E}_{kerosene} = \frac{\left({prod}_{RFNBO-H_2} + {prod}_{LC-H_2} \right) \times {CI}_{H2} + el_{grid\_shift}  \times CI_{grid\_shift}}{{En}_{output}  \times  \eta_{FT}} \approx 21.4\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{kerosene}\right.}
$$

??? success "Threshold reached"
    The threshold of $28.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}$ is met. We can declare the fuel as RFNBO (or low carbon fuel).

Share of RFNBO in the output is 

$$
Share_{RFNBO- H2} = \frac{{prod}_{RFNBO-H_2}}{{prod}_{RFNBO-H_2} + {prod}_{LC-H_2}} \approx 91\color{grey}{\%}
$$


??? info "If looking only at the shift reaction"
    Energy coming out of the shift reaction: 

    $$
    {En}_{output} = \left({prod}_{RFNBO-H_2} + {prod}_{LC-H_2} \right) \times \eta_{shift} + el_{grid\_shift} \times Share_{heat\_to\_heating\_value} = 334.7\ \color{grey}{GJ}
    $$

    This is higher than the hydrogen input, so the electricity has to be considered a relevant input.


    Share of RFNBO in the output is 

    $$
    Share_{RFNBO-kerosene} = \frac{{prod}_{RFNBO-H_2}}{{prod}_{RFNBO-H_2} + {prod}_{LC-H_2} + el_{grid\_shift}} \approx 73\color{grey}{\%}
    $$

    Total GHG intensity as before:

    $$
    {E}_{kerosene} \approx 27.7\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{kerosene}\right.}
    $$



## Conclusion

This case study shows that if looking at the processes separately, under certain circumstances it is possible that the energy content is increased, and that the electricity has to be counted as relevant input. In this case, the share of RFNBO in the output changes, but the GHG intensity remains the same.

# R3: Biofuels and RFNBO co-production

-   How to split biogenic and RFNBO-parts

![](../images/r3_biogenic co-production.svg)

Instead of using a shift reaction to increase the H~2~/CO ratio in biogenic syngas, RFNBO hydrogen is added to the Fischer-Tropsch process. According to the “co-processing exception” in Annex A point 1, a distinction on a proportional basis of the energetic value of inputs shall be made.

As clarified in the [Q&A document](https://circabc.europa.eu/ui/group/8f5f9424-a7ef-4dbf-b914-1af1d12ff5d2/library/ca8efd4d-cb44-4aec-914d-3d95f95ea293/details), the process can be split using the share of RFNBO hydrogen in overall hydrogen input to determine the share of all products going into the part of the process following the RFNBO GHG methodology.

## Assumptions

| Parameter                   |    Symbol          | Example value |
|----------------------------|:--------------:|:-----------------------:|
|H2:CO ratio of biogenic syngas | $r_{bio}$ | $1:1$ |
|Molar ratio of biogenic syngas to RFNBO hydrogen | $r_{sh}$ | $1:1$ |
|(H2:CO ratio for FT reaction | $r_{FT}$ | $3:1$ )|
|Molar LHV hydrogen | $lhv_{H_2}$ | $244\ \color{grey}{\left.MJ\middle/kmol\right.}$ |
|Molar LHV CO | $lhv_{CO}$ | $283\ \color{grey}{\left.MJ\middle/kmol\right.}$ |
|Efficiency of the FT reaction | $\eta_{FT}$ | $70\color{grey}{\%}$ |
|RFNBO hydrogen GHG intensity | $CI_{H_2}$ | $5\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{el}\right.}$ |
|Biogenic syngas GHG intensity | $CI_{bio\_syngas}$ | $20\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{syngas}\right.}$ |

## Calculation

Energy in 1 kmol of syngas: $En_{syngas} =  263.5\ \color{grey}{\left.MJ\middle/kmol\right.}$

Energy in 1 kmol of hydrogen: $En_{H_2} =  283\ \color{grey}{\left.MJ\middle/kmol\right.}$

Energy share of RFNBO in the inputs: $s_{RFNBO} = \frac{En_{H_2}}{En_{syngas} + En_{H_2}} \approx 51.8 \color{grey}{\%}$

This share will be used to split the process: all RFNBO hydrogen and 51.8% of the CO will go into the process part calculated according to the RFNBO GHG methodology.

To simplify the example, we assume no process emissions. $e_u$ determined from emission factor.

Total GHG intensity:

$$
\begin{aligned}
{E}_{RFNBO-kerosene} &= \left(e_{i,elastic} + e_{i,rigid} - e_{ex-use}\right) + e_p + e_{td} + e_u - e_{ccs}
\\
e_{i,rigid},\ e_p,\ e_{td},\ e_{ccs} &&= 0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\\
e_{i,elastic} &= \frac{r_{FT} \times CI_{H_2} + CI_{bio\_syngas}}{\left(r_{FT} + 1\right) \times \eta_{FT}} &\approx 12.5\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{kerosene}\right.}
\\
e_u &&= 68.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{kerosene}\right.}
\\
e_{ex-use} &&= 68.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{kerosene}\right.}
\\
{E}_{RFNBO-kerosene} &= \frac{CI_{ren}}{\eta_{FT}} &= 0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{kerosene}\right.}
\end{aligned}
$$

Ex-use is attributed because the carbon going into the RFNBO-kerosene is not fossil (see [Q&A document](https://circabc.europa.eu/ui/group/8f5f9424-a7ef-4dbf-b914-1af1d12ff5d2/library/ca8efd4d-cb44-4aec-914d-3d95f95ea293/details))

$$
\begin{aligned}
{E}_{bio-kerosene} &= \frac{CI_{bio\_syngas}}{\eta_{FT}} = \ 28.6\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{kerosene}\right.}
\end{aligned}
$$

??? success "Threshold reached for RFNBO"
    The threshold of $28.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}$ is met. We can declare the fuel as RFNBO (or low carbon fuel). Different thresholds apply for the biofuel.

Share in the output (see above): 

$$
\begin{aligned}
Share_{RFNBO-kerosene} &= 51.8\color{grey}{\%} \\
Share_{bio-kerosene} &= 48.2\color{grey}{\%}
\end{aligned}
$$

## Conclusion

This case study shows that the streams are separated based on the energy in the inputs, and then the GHG intensity is calculated for each stream separately.

# R4: Partly replacing fossil inputs

-   How to split RFNBO part from fossil inputs in existing fossil processes

![](../images/r4_splitting fossil.svg)

Very similar to the [biogenic syngas case](#r3-biofuels-and-rfnbo-co-production), the fossil process part can be virtually split from the RFNBO part. Here, we show a case of coal gasification and Fischer Tropsch synthesis, but this could be applied to other fossil transformation processes.

??? tip "Allocation to Fischer Tropsch co-products"
    It is not possible to freely allocate the RFNBO share to one of the co-products, for example kerosene. All FT products contain the same share of RFNBO.

## Assumptions

| Parameter                   |    Symbol          | Example value |
|----------------------------|:--------------:|:-----------------------:|
|Energy ratio of syngas to hydrogen | $r_{sh}$ | $9\ \color{grey}{\left.MJ_{syngas}\middle/MJ_{hydrogen}\right.}$ |
|Efficiency of the FT reaction | $\eta_{FT}$ | $70\color{grey}{\%}$ |
|Fully renewable electricity GHG intensity | $CI_{ren}$ | $0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{el}\right.}$ |
|Fossil syngas GHG intensity | $CI_{syngas}$ | $120\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{syngas}\right.}$ |

## Calculation

Total GHG intensity: 

$$
\begin{aligned}
{E}_{RFNBO-kerosene} &= 0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{kerosene}\right.} \\
{E}_{fossil-kerosene} &= \frac{CI_{syngas}}{\eta_{FT}} = 171.4\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{kerosene}\right.}
\end{aligned}
$$

??? success "Threshold reached for RFNBO"
    The threshold of $28.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}$ is met. We can declare the fuel as RFNBO (or low carbon fuel). The impact of the fossil process remains as before.

Share of RFNBO in the output is $Share_{RFNBO-kerosene} = \frac{1}{1 + r_{sh}} = 10\color{grey}{\%}$

## Conclusion

Even if the fossil part doesn’t respect the 70% GHG reduction, the energetic share of RFNBO in the inputs can still be virtually split from the process and the corresponding output can be declared as RFNBO.

# R5: Allocation to co-produced heat

-   How to allocate e_ex_use to co-products that don't contain carbon

![](../images/r5_heat allocation.svg)

In this virtual case, the sum of all emissions that should be allocated between the product (methane) and the useful heat is negative because of the e$_{ex-use}$ credit for CO$_2$ included in e$_i$. Allocating negative emissions to heat may be undesired. The reply to question 50 of the guidance document allows for allocation according to the same rules as set out for biofuels in Annex V to the RED.

## Assumptions

| Parameter                   |    Symbol          | Example value |
|----------------------------|:--------------:|:-----------------------:|
|GHG intensity of hydrogen | $e_{hydrogen}$ | $8\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{methane}\right.}$ |
|GHG intensity of CO$_2$ | $e_{CO_2}$ | $1\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{methane}\right.}$ |
|Ex-use for CO$_2$ | $e_{ex-use}$ | $10\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{methane}\right.}$ |
|Heat production efficiency | $\eta_{heat}$ | $99\ \color{grey}{\%}$ |
|Energy ratio of useful heat to methane | $r_{hm}$ | $0.1\ \color{grey}{\left.MJ_{useful\ heat}\middle/MJ_{methane}\right.}$ |

## Calculation

Emissions to be allocated don't include e_u:

$$
\begin{aligned}
{E}_{products} &= \left(e_{i,elastic} + e_{i,rigid} - e_{ex-use}\right) + e_p + e_{td} - e_{ccs}
\\
e_{i,rigid},\ e_{p},\ e_{td},\ e_{ccs} &&= 0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{methane}\right.}
\\
e_{i,elastic} &= e_{hydrogen} + e_{CO_2} &= 9\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{methane}\right.}
\\
{E}_{products} &= e_{i,elastic} - e_{ex-use} &= -1\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{methane}\right.}
\end{aligned}
$$

With normal energy allocation, this gives:

$$
\begin{aligned}
{E}_{heat}  &= \frac{{E}_{products}}{1 + r_{hm}} &= -0.9\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{product}\right.}
\\
{E}_{methane} &= \frac{{E}_{products}}{1 + r_{hm}} + e_u &= 9.1\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{product}\right.}
\end{aligned}
$$

RED II Annex V part C point 17 allows: ...The greenhouse gas intensity of excess useful heat or excess electricity is the same as the greenhouse gas intensity of heat or electricity delivered to the fuel production process...

The heat needed for the process comes entirely from the hydrogen, so:

$$
\begin{aligned}
{E}_{heat} &= \frac{e_{hydrogen}}{\eta_{heat}} &\approx 8.1\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{useful\ heat}\right.}
\\
{E}_{methane} &= {E}_{products} - {E}_{heat} \times r_{hm} + e_u &\approx 8.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{useful\ heat}\right.}
\end{aligned}
$$

??? success "Threshold reached for RFNBO"
    The threshold of $28.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}$ is met. We can declare the fuel as RFNBO (or low carbon fuel).

## Conclusion

Negative emissions from e_ex-use should not be allocated to products that don't contain carbon (and thus don't have combustion emissions), as negative emissions don't make physical sense.


# R6: Full example

-   How to combine the previous examples and where to find additional information.

![](../images/r6-optimized.svg)

For the hydrogen production, refer to [hydrogene example](#h3-hydrogen-full-example)

??? "CO~2~ source"
    ## CO~2~ source
    
    ### Eligibility for the e~ex\ use~ “credit”
    
    -   The carbon incorporated into the fuel can be counted as negative emissions if it would have otherwise been emitted as CO~2~ to the atmosphere and stems from air capture, biofuel, RCF or RFNBO production or combustion or an already emitting geological source. Until 2035, also fossil CO~2~ is eligible if taken into account in an effective carbon pricing system. [GHG.10](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q36](../FAQ/faq.md#Q36) [Q37](../FAQ/faq.md#Q37) [Q38](../FAQ/faq.md#Q38) [Q39](../FAQ/faq.md#Q39) [Q40](../FAQ/faq.md#Q40) [Q41](../FAQ/faq.md#Q41) [Q43](../FAQ/faq.md#Q43) [Q42](../FAQ/faq.md#Q42) [Q43](../FAQ/faq.md#Q43) [Q44](../FAQ/faq.md#Q44) [Q-Annex3](https://energy.ec.europa.eu/document/download/21fb4725-7b32-4264-9f36-96cd54cff148_en?filename=2024%2003%2014%20Document%20on%20Certification.pdf)
    
    ### Example in this case study
    
    The CO~2~ comes from a biomass boiler.
    
    | Parameter                   |    Symbol          | Example value |
    |----------------------------|:--------------:|:-----------------------:|
    |Emissions from CO~2~ capture and supply | $CI_{CO2}$ | $3.6\ \color{grey}{\left.g\,CO_2\,eq\middle/kg\ CO_{2}\right.}$ |
        
    
    
??? "Methanol production"
    ## Methanol production
    
    ### Example in this case study
    
    The inputs are supplied by the processes described above, the auxiliaries use grid electricity. We assume no additional non-biogenic GHG emissions in the process.
    
    | Parameter                   |    Symbol          | Example value |
    |----------------------------|:--------------:|:-----------------------:|
    |Input of hydrogen | $meoh_{H2}$ | $1.2\ \color{grey}{\left.MJ_{H2}\middle/MJ_{MeOH}\right.}$ |
    |GHG intensity of hydrogen | ${CI}_{H2}$| $4.3\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ\right.}$ |
    |Input of CO~2~ | $meoh_{CO2}$ | $0.075\ \color{grey}{\left.kg\ CO_{2}\middle/MJ_{MeOH}\right.}$ |
    |Input of electricity | $meoh_{el}$ | $0.05\ \color{grey}{\left.MJ_{el}\middle/MJ_{MeOH}\right.}$ |
    |Share of RFNBO in the output | $Share_{RFNBO- MeOH}$ | $91\color{grey}{\%}$ |
    |Conversion rate of CO~2~ | $conv_{CO2}$ | $90\color{grey}{\%}$ |
    
    Total GHG intensity: 
    
    $${CI}_{MeOH} = meoh_{h2} \times CI_{H2} + \frac{meoh_{CO2}}{conv_{CO2}}\ CI_{CO2} + meoh_{el} \times CI_{grid} \approx 6.8\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{MeOH}\right.}$$
        
    
    
??? "Fuel transport"
    ## Fuel transport
    
    ### Emissions
    
    -   Emissions of transport should be allocated based on the emissions attributable to the RFNBO (generally by energy, mass or volume of the overall transported fuel). This includes empty return trips. [GHG.1](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q58](../FAQ/faq.md#Q58) 
    
    ### Example in this case study
    
    The ship is loaded with 80% of the methanol produced in this pathway and 20% fossil methanol. The return trip is empty. Transport emissions are calculated by dividing the overall emissions of both trips by the overall fuel transported and allocated by energy to all fuels.

    | Parameter                   |    Symbol          | Example value |
    |----------------------------|:--------------:|:-----------------------:|
    |Emissions caused by transport | $e_{transp}$ | $1\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{fuel\_transported}\right.}$|

    !!! info "Transport emissions calculation"
        In general, the emissions shall be calculated by calculating the overall emissions caused by all transport operations, including empty return trips and fugitive emissions. All emissions, also for upstream fuel production, should be included. They should then be attributed to all transported products.
        
    !!! info "Using the transported fuel"
        If the ship uses part of the transported fuel to propell itself, the amount arriving at destination is lower than the amount charged. In that case, the calculation should obviously take into account the upstream and combustion emissions from the fuel burnt in the ship, in the current example a mix of the RFNBO and fossil methanol, and should allocate them to the amount of fuel that arrives at destination.

    
    Total GHG intensity: ${CI}_{MeOH\_ transported} = {CI}_{MeOH} + e_{transp} \approx 7.8\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{MeOH\_at\_destination}\right.}$
        
    
    
??? "Hydrogen and oxygen production"
    ## Hydrogen and oxygen production
    
    ### Allocation of emissions to products without energy content
    
    -   If oxygen is sold as a product, emissions can be allocated to it by economic value (average factory-gate value of the products over the last three years). [GHG.15](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q49](../FAQ/faq.md#Q49) 
    
    ### Example in this case study

    | Parameter                   |    Symbol          | Example value |
    |----------------------------|:--------------:|:-----------------------:|
    |Mass ratio of oxygen to hydrogen| $m_{O2}$ | $8\ \color{grey}{\left.kg\ {O}_{2}\middle/kg\ H_{2}\right.}$|    
    |Average factory-gate price of hydrogen| $p_{H2}$ | $5\ \color{grey}{\left.\unicode{x20AC}\middle/kg\ H_{2}\right.}$|
    |Average factory-gate price of oxygen| $p_{O2}$ | $0.1\ \color{grey}{\left.\unicode{x20AC}\middle/kg\ O_{2}\right.}$|
    |Total emissions for electrolysis (in this case assumed to be only from electrolysis)|$e_{ely\_aux}$ | $0.5\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{H2}\right.}$|
    
    Allocation of emissions to hydrogen: 
    
    $$alloc_{H2} = \frac{p_{H2}}{p_{O2}m_{O2} + p_{H2}} \approx 86\color{grey}{\%}$$
    
    Emissions attributed to hydrogen: $e_{ely\_ H2} = e_{ely\_aux} \times alloc_{H2} \approx 0.43\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{H2}\right.}$
        
    
    
??? "Use of waste heat"
    ## Use of waste heat
    
    ### Waste heat as rigid input
    
    -   If waste heat from another process is used as energy input, and the waste heat production cannot be increased and does not represent 10% of the economic value or more, it can be considered a rigid input with no emissions attributed to it. [GHG.4](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q45](../FAQ/faq.md#Q45) 
    
    ### Example in this case study
    
    The heat in the case study can be considered waste heat with no emissions.
    
??? "Final fuel production"
    ## Final fuel production
    
    ### Share of RFNBO in each output stream
    
    -   The share of RFNBO in all outputs should be equal. [RED II 30](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=uriserv:OJ.L_.2018.328.01.0082.01.ENG#030.002) [Q-Annex2](https://energy.ec.europa.eu/document/download/21fb4725-7b32-4264-9f36-96cd54cff148_en?filename=2024%2003%2014%20Document%20on%20Certification.pdf)[Q47](../FAQ/faq.md#Q47) [Q51](../FAQ/faq.md#Q51) [Q52](../FAQ/faq.md#Q52) 
    
    ### Share of overall RFNBO in the output
    
    -   If the additional hydrogen is an RFNBO and increases the heating value of the outputs, it also increases the share of RFNBO in the output. [Q53](../FAQ/faq.md#Q53) [Q57](../FAQ/faq.md#Q57) 
    
    ### Other sectors than transport
    
    -   According to the new RED, RFNBO terminology can also be used in other sectors. [RED II rev](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32023L2413) [Q10](../FAQ/faq.md#Q10) 
    
    ### Example in this case study
    
    For illustration purposes, the methanol-to-synfuels process is modified and simplified to only produce diesel and kerosene and only use methanol, hydrogen and heat as inputs. In this example, we assume that the heat is not contributing to the heating value of the fuel.

    | Parameter                   |    Symbol          | Example value |
    |----------------------------|:--------------:|:-----------------------:|
    |Energy share of diesel in output| $Share_{diesel}$ | $44\color{grey}{\%}$    |
    |Energy share of kerosene in output| $Share_{kerosene}$ | $56\color{grey}{\%}$  |  
    |Input of methanol| $fuel_{MeOH}$ | $1.1\ \color{grey}{\left.MJ\ MeOH\middle/MJ\ fuel\right.}$    |
    |Input of hydrogen| $fuel_{H2}$ | $0.1\ \color{grey}{\left.MJ\ H_{2}\middle/MJ\ fuel\right.}$    |
    |Share of RFNBO in hydrogen input| $Share_{RFNBO-H2}$ | $100\color{grey}{\%}$    |    
    |Input of heat| $fuel_{heat}$ | $0.2\ \color{grey}{\left.MJ\ heat\middle/MJ\ fuel\right.}$    |
    
    Emissions attributed to all fuels:
    
    $$E = CI_{fuels} = {fuel}_{MeOH} \times {CI}_{MeOH\_transported} + {fuel}_{h2} \times CI_{H2} + {fuel}_{heat} \times CI_{heat} \approx 8.6\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{fuel}\right.}$$
    
    Emission reduction compared to the fossil fuel comparator: 
    
    $$Savings = \frac{E_{F} - E}{E_{F}} = \frac{94 - 8.6}{94} \approx 91\color{grey}{\%}$$

    Share of RFNBO: 
    
    $$Share_{RFNBO-fuels} = \frac{Share_{RFNBO-MeOH} \times {fuel}_{MeOH} + Share_{RFNBO-H2} \times \ {fuel}_{H2}}{{fuel}_{MeOH} + {fuel}_{H2}} \approx 92\color{grey}{\%}$$
    