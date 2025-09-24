# 1: Water electrolysis, pure fully renewables

-   How to allocate emissions to oxygen

-   How to calculate the share of RFNBO with emissions from auxiliaries

<img src="../images/cs1_allocation.svg" style="width:50%" />

Fully renewable electricity is attributed zero GHG emissions. Therefore, the only emissions come from auxiliaries.

They are allocated to the co-products by the economic value (15(f), because oxygen has no energy content).

## Assumptions:

| Parameter                   |    Symbol          | Example value           |
|----------------------------|:--------------:|:------------------------:|
| Efficiency of the electrolyser | $\eta_{ely}$ | $60\%$ |
| economic value of RFNBO hydrogen | $v_{hydrogen}$  | $6\ \frac{\unicode{x20AC}}{{kg}_{hydrogen}}$   |
| economic value of oxygen | $v_{oxygen}$ | $0.3\ \frac{\unicode{x20AC}}{{kg}_{oxygen}}$  |
| mass of produced oxygen per kg of hydrogen | $r_{oh}$ | $8\ \frac{{kg}_{oxygen}}{{kg}_{hydrogen}}$ |
| Fully renewable electricity carbon intensity | $ci_{ren}$ | $0\ \frac{g\ CO_{2}eq}{kWh}$ |
| Auxiliaries carbon intensity | $ci_{aux}$ | $5\ \frac{g\ CO_{2}eq}{{MJ}_{hydrogen}}$   |

## Calculation:

Emissions attributed to hydrogen: $E = ci_{ren}*\eta + {ci}_{aux}*\frac{v_{hydrogen}}{v_{hydrogen} + v_{oxygen}*r_{oh}} = 3.57\frac{g\ CO_{2}eq}{{MJ}_{hydrogen}}\ $

Share of RFNBO in the output is $s_{RFNBO\_H2} = 100\%$

## Conclusion:

This case study shows that the share of RFNBO is calculated on the energy share of relevant inputs, while emissions are calculated based on all emissions, including auxiliaries. The emissions can be attributed to co-products, in case of products without energy content, economic allocation is used.

# 2: Fully renewable and grid electricity

-   How to average over different timeframes

<img src="../images/cs2_grid.svg" style="width:50%" />

Electrolyser running at 764 MW with a mix of mostly renewable electricity, complemented by grid electricity.

## Assumptions:

| Parameter                   |    Symbol          | Monthly averaging                | Hourly averaging |
|----------------------------|--------------|:----------------:|:---------------:|
| Grid carbon intensity | $ci_{grid}$                  | $100 \frac{g\ CO_{2}eq}{kWh}$  {: colspan=2} |
| Relevant renewable electricity used | $el_{ren}$     | $500\ GWh$                     | $264\ MWh$     |
| Relevant grid electricity used | $el_{grid\_ely}$ | $50\ GWh$                      | $500\ MWh$     |
| Grid electricity for auxiliaries | $el_{grid\_aux}$ | $0.5\ GWh$                     | $0.7\ MWh$     |
| Efficiency of the electrolyser | $\eta_{ely}$        | $60\%$                         {: colspan=2} |

## Calculation:

### Monthly averaging:

Share of RFNBO in the output is $s_{RFNBO\_H2} = \frac{el_{ren}}{el_{ren} + {el}_{grid\_ely}\ \ \ } = \frac{500\ GWh}{550\ GWh} \approx 91\%$

Total carbon intensity: ${ci}_{H2} = \frac{\left( {el}_{grid\_ ely} + el_{grid\_aux} \right) * ci_{grid}}{\left( el_{ren} + {el}_{grid\_ely} \right)\ \eta_{ely}} = \frac{50.5\ GWh*100\ g/kWh}{550\ GWh*60\%} \approx 4.3\frac{g\ CO_{2}eq}{MJ}$

### Hourly averaging, low renewables:

Total carbon intensity: ${ci}_{H2} = \frac{\left( {el}_{grid\_ely} + el_{grid\_aux} \right) * ci_{grid}}{\left(el_{ren} + {el}_{grid\_ely} \right) * \eta_{ely}} = \frac{500.7\ MWh*100\frac{g}{kWh}}{764\ MWh*60\%} \approx 30.3\frac{g\ CO_{2}eq}{MJ}$

Share of RFNBO in the output is $s_{RFNBO\_ H2} = 0\%$ because threshold of $28.2 \frac{g}{MJ}$ is not met.

## Conclusion:

This case study shows how averaging over shorter time scales can exclude some periods with low renewables from the RFNBO production. In other cases that are not shown here, the contrary could happen that the average over a longer period has a too high carbon intensity to qualify.

# 3: Ammonia + cracking

-   How to determine if an energy input is “relevant”

<img src="../images/cs3_ammonia_relevant energy.svg" style="width:50%" />

Cracking Ammonia is endothermic, the heat can be supplied electrically or by burning part of the ammonia. Here we assume that the energy is supplied electrically.

## Assumptions:

| Parameter                   |    Symbol          | Example value |
|----------------------------|:--------------:|:---------------------:|
|Hydrogen demand Haber process (ammonia production) | ${hydrogen}_{input}$ | $1.16 \frac{MJ_{H_{2}}}{MJ_{{NH}_{3}}}$ |
|Ammonia demand for cracking | ${ammonia}_{input}$ | $0.88 \frac{MJ_{NH_{3}}}{MJ_{H_{2}}}$ |
|Electricity demand Haber process | $el_{grid\_Haber}$ | $0.75 \frac{MJ_{el}}{MJ_{NH_{3}}}$ |
|Electricity demand cracking process | $el_{grid\_cracking}$ | $0.3 \frac{MJ_{el}}{MJ_{H_{2}}}$ |
|Grid carbon intensity | $ci_{grid}$ | $100 \frac{g\ CO_{2}eq}{kWh}$ |

As the output energy is bigger than the input energy, the electricity used in the cracking process needs to be considered as a relevant input.

## Calculation:

Total carbon intensity: ${ci}_{H_{2}} = \left( {ammonia}_{input}*el_{grid\_Haber} + el_{grid\_cracking} \right)*ci_{grid} \approx 26.7\frac{g\ CO_{2}eq}{MJ}$

Share of RFNBO in the output is $s_{RFNBO\_H_{2}} = \frac{{ammonia}_{input} * {hydrogen}_{input}}{{{ammonia}_{input} * hydrogen}_{input}  +  el_{grid\_cracking}} = \frac{1.02\ MJ}{1.02 + 0.3\ MJ} \approx 77\%$

## Conclusion:

This case study shows that some transport processes that need energy to split the transported product at destination might need to consider the energy needed for the split as relevant energy. If this energy is not fully renewable, the share of RFNBO will decrease.

# 4: rWGS+FT to kerosene

-   How to count different integrated processes together

<img src="../images/cs4_integrated rWGS and FT.svg" style="width:50%" />

Hydrogen production as before, shift with CO~2~ and FT to kerosene, assuming only kerosene as output to simplify the example.

The shift reaction and Fischer Tropsch can be either seen as an integrated process, or as two separate processes. It is allowed to choose either one. We first calculate if the reaction adds to the heating value, in which case the grid electricity used for heating the reactor has to be counted as relevant input.

## Assumptions:

| Parameter                   |    Symbol          | Example value |
|----------------------------|:--------------:|:---------------------:|
|Relevant renewable electricity used | $el_{ren}$     | $500\ GWh$                     |
|Relevant grid electricity used | $el_{grid\_ely}$ | $50\ GWh$                      | 
|Grid electricity for auxiliaries | $el_{grid\_aux}$ | $0.5\ GWh$      |
|Efficiency of the electrolyser | $\eta_{ely}$        | $60\%$ |
|Amount of hydrogen produced | ${prod}_{H2}$ | $\left( el_{ren} + el_{grid\_ely} \right) * \eta_{ely} = 550\ GWh*60\% = 330\ GWh$ |
|Hydrogen carbon intensity | ${ci}_{H2}$ | $30.3\frac{g\ CO_{2}eq}{MJ}$ |
|Relevant grid electricity used for the shift reaction | $el_{grid\_shift}$ | $80\ GWh$ |
|Share of the (electric) heat energy ending up in the syngas | $s_{heat\_to\_heating\_value}$ | $10\%$ |
|Efficiency of the shift reaction | $\eta_{shift}$ | $ 99\%$ |
|Shift reaction grid carbon intensity | $ci_{grid\_shift}$ | $18 \frac{g\ CO_{2}eq}{kWh}$ |
|Efficiency of the FT reaction | $\eta_{FT}$ | $70\%$ |

## Calculation:

### If looking only at the shift reaction:

Energy coming out of the shift reaction: ${En}_{output} = {prod}_{H2}*\eta_{shift} + el_{grid\_shift}*s_{heat\_to\_heating\_value} = 334.7\ GWh$

This is higher than the hydrogen input, so the electricity has to be considered a relevant input.

Total carbon intensity: ${ci}_{kerosene} = \ \frac{\left( el_{grid\_ely} + el_{grid\_aux} \right)\ *\ ci_{grid} + el_{grid\_shift} * ci_{grid\_shift}}{{En}_{output} * \eta_{FT}} = \frac{50.5\ GWh*100\frac{g}{kWh} + 80\ GWh*18\ g/kWh}{334.7\ GWh*70\%} \approx 27.7\frac{g\ CO_{2}eq}{MJ}$

Share of RFNBO in the output is $s_{RFNBO\_ kerosene} = \ \frac{el_{ren}}{el_{ren} + el_{grid\_ely} + el_{grid\_ shift\ }} = \frac{500\ GWh}{630\ GWh} \approx 79\%$

### If looking at the shift and FT reaction as an integrated process:

Energy coming out of the FT reaction: ${En}_{output} = \left( {prod}_{H2}*\eta_{shift} + el_{grid\_shift}*s_{heat\_to\_heating\_value} \right) * \eta_{FT} = 234.3\ GWh$

This is lower than the hydrogen input, so the electricity does not have to be considered a relevant input.

Total carbon intensity as before: ${ci}_{kerosene} \approx 27.7\frac{g\ CO_{2}eq}{MJ}$

Share of RFNBO in the output is $s_{RFNBO\_ H2} = \frac{el_{ren}}{el_{ren} + {el}_{grid\_ely}} = \frac{500\ GWh}{550\ GWh} \approx 91\%$

## Conclusion:

This case study shows that if looking at the processes separately, under certain circumstances it is possible that the energy content is increased, and that the electricity has to be counted as relevant input. In this case, the share of RFNBO in the output changes, but the carbon intensity remains the same.

# 5: Biogenic syngas with surplus CO and RFNBO hydrogen

-   How to split biogenic and RFNBO-parts

<img src="../images/cs5_biogenic co-production.svg" style="width:50%" />

Instead of using a shift reaction to increase the H~2~/CO ratio in biogenic syngas, RFNBO hydrogen is added to the Fischer-Tropsch process. According to the “co-processing exception” in Annex A point 1, a distinction on a proportional basis of the energetic value of inputs shall be made.

## Assumptions:

| Parameter                   |    Symbol          | Example value |
|----------------------------|:--------------:|:-----------------------:|
|Energy ratio of syngas to hydrogen | $r_{sh}$ | $4\ \frac{MJ_{syngas}}{MJ_{hydrogen}}$ |
|Efficiency of the FT reaction | $\eta_{FT}$ | $70\%$ |
|Fully renewable electricity carbon intensity | $ci_{ren}$ | $0\ \frac{g\ CO_{2}eq}{kWh}$ |
|Biogenic syngas carbon intensity | $ci_{bio\_syngas}$ | $20\ \frac{g\ CO_{2}eq}{{MJ}_{syngas}}$ |

## Calculation:

Total carbon intensity: ${ci}_{RFNBO - kerosene} = 0 \frac{g\ CO_{2}eq}{MJ}$

${ci}_{bio-kerosene} = \frac{ci_{bio\_syngas}}{\eta_{FT}} = \ 28.6 \frac{g\ CO_{2}eq}{MJ}$

Share of RFNBO in the output is $s_{RFNBO\_kerosene} = \ \frac{1}{1 + r_{sh}} = 0.2$

## Conclusion:

This case study shows that the streams are separated based on the energy in the inputs, and then the carbon intensity is calculated for each stream separately.

# 6: Partly replacing fossil inputs like in coal Fischer Tropsch

-   How to split RFNBO part from fossil inputs

<img src="../images/cs6_splitting fossil.svg" style="width:50%" />

Very similar to the biogenic syngas case, the fossil process part can be virtually split from the RFNBO part.

## Assumptions:

| Parameter                   |    Symbol          | Example value |
|----------------------------|:--------------:|:-----------------------:|
|Energy ratio of syngas to hydrogen | $r_{sh}$ | $9\ \frac{MJ_{syngas}}{MJ_{hydrogen}}$ |
|Efficiency of the FT reaction | $\eta_{FT}$ | $70\%$ |
|Fully renewable electricity carbon intensity | $ci_{ren}$ | $0\ \frac{g\ CO_{2}eq}{kWh}$ |
|Fossil syngas carbon intensity | $ci_{syngas}$ | $120\ \frac{g\ CO_{2}eq}{{MJ}_{syngas}}$ |

## Calculation:

Total carbon intensity: ${ci}_{RFNBO-kerosene} = 0\ \frac{g\ CO_{2}eq}{MJ}$

${ci}_{fossil-kerosene} = \frac{ci_{syngas}}{\eta_{FT}} = \ 171.4\ \frac{g\ CO_{2}eq}{MJ}$

Share of RFNBO in the output is $s_{RFNBO\_kerosene} = \ \frac{1}{1 + r_{sh}} = 0.1$

## Conclusion:

Even if the fossil part doesn’t respect the 70% GHG reduction, the energetic share of RFNBO in the inputs can still be virtually split from the process and the corresponding output can be declared as RFNBO.

# 7: Full example: Mixed RFNBO and low-carbon hydrogen transported as methanol to EU and transformed to diesel and kerosene

-   How to combine the previous examples and where to find additional information.

![](images/cs1-optimized.svg)

??? "Renewable electricity production"
    ## Renewable electricity production
    
    ### Requirements to qualify as renewable
    
    -   **Direct connection** if renewable production generating installation came into operation not earlier than 36 months before the installation producing renewable liquid and gaseous transport fuel of non-biological origin [ADD.3](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_3) [Q12](faq.md#Q12) [Q13](faq.md#Q13) [Q14](faq.md#Q14) 
    
    -   In a **bidding zone** where the average proportion of **renewable electricity exceeded 90%** in the previous calendar year (and for the five following years). Limited to full load hours \< 8760 hours x RES-E share [ADD.4](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_4) [Q15](faq.md#Q15) [Q16](faq.md#Q16) [Q17](faq.md#Q17) 
    
    -   In a **bidding zone** where the **emission intensity of electricity is lower than 18 gCO2eq/MJ** with renewable PPAs and temporal and geographical correlation [ADD.4](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_4)
    
    -   During **imbalance settlement period** [ADD.4](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_4) [Q18](faq.md#Q18) 
    
    -   If additionality, temporal correlation and geographical correlation are met [ADD.5](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_5) [ADD.6](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_6) [ADD.7](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_7) [Q19](faq.md#Q19) [Q20](faq.md#Q20) [Q21](faq.md#Q21)  [Q22](faq.md#Q22) [Q23](faq.md#Q23) [Q24](faq.md#Q24) [Q25](faq.md#Q25) [Q26](faq.md#Q26) [Q27](faq.md#Q27) [Q28](faq.md#Q28) [Q29](faq.md#Q29) 
    
    ### Combination of options
    
    -   All sourcing options can be combined, but if electricity is used in a time period that does not qualify as renewable, a share of the output equal to this electricity share in the inputs will not be an RFNBO. [Q30](faq.md#Q30) 
    
    ### What electricity inputs are considered
    
    -   To define the share of RFNBO produced, the share of electricity that counts as renewable in all relevant inputs is considered. Relevant inputs are inputs contributing to the energy content of the fuel. [GHG.3](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q61](faq.md#Q61) [Q62](faq.md#Q62) [Q67](faq.md#Q67) [Q68](faq.md#Q68) 
    
    ### Temporal aspects
    
    -   Temporal correlation of renewable electricity production and RFNBO production is necessary if they are not connected through a direct connection.
    
    -   The time period over which a “batch” of fuel (with the same carbon intensity) is produced can be up to one month, but needs to be in line with the requirements applying for temporal correlation. [GHG.1](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q67](faq.md#Q67) 
    
    ### Geographical aspects
    
    -   Geographical correlation of renewable electricity production and RFNBO production is necessary if they are not connected through a direct connection.
    
    -   Geographical correlation is given if electricity producer and electrolyser are in the same bidding zone, or in an interconnected bidding zone while the electricity price in the zone with the electrolyser is lower than in the interconnected bidding zone, or the renewable energy is produced in an interconnected offshore bidding zone. [ADD.7](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_7)
    
    ### Example in this case study
    
    Renewable electricity is sourced in the third country via a direct connection and a PPA with additionality, temporal and geographical correlation are met. The relevant time period considered is one month.
   
    Total carbon intensity: $ci_{ren} = 0\ \frac{g\ CO_{2}eq}{kWh}$
        
    
    
??? "Grid electricity"
    ## Grid electricity
    
    ### Grid electricity used in electrolyser
    
    -   If grid electricity is used in the same time period as renewable electricity, the output contains a share of RFNBO and a share of (low-carbon) fuel proportional to the energy input. [GHG.3](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1)
    
    -   The carbon intensity of grid electricity can be calculated using the methodology in [C](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#d1e825-23-1)
    
    ### Auxiliaries powered by grid electricity
    
    Auxiliaries can be powered by grid electricity. The emission intensity of this electricity has to be taken into account, but the share of RFNBO in the output is not affected. [GHG.3](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q11](faq.md#Q11) 
    
    ### Example in this case study
    
    Total carbon intensity: $ci_{grid} = 100\ \frac{g\ CO_{2}eq}{kWh}$
        
    
    
??? "Electrolysis"
    ## Electrolysis
    
    ### Share of RFNBO
    
    The share of RFNBO is calculated for each processing step based on the share of the relevant energy inputs. [GHG.8](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1)
    
    ### Carbon intensity
    
    -   All fuel outputs have the same carbon intensity [GHG.1](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q55](faq.md#Q55) 
    
    -   The carbon intensity is calculated by dividing all emissions by the overall energy in the fuel. [GHG.1](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1)
    
    ### Example in this case study
    
    The relevant time period considered is one month.
    
    Relevant renewable electricity used: $el_{ren} = 500\ GWh$
    
    Relevant grid electricity used: $el_{grid\_ ely\ } = 50\ GWh$
    
    Grid electricity for auxiliaries: $el_{grid\_ aux} = 0.5\ GWh$
    
    Efficiency of the electrolyser $\eta_{ely} = 60\%$
    
    Share of RFNBO in the output is $s_{RFNBO\_ H2} = \ \frac{el_{ren}}{el_{ren} + {el}_{grid\_ ely}\ \ \ } = \frac{500\ GWh}{550\ GWh} \approx 91\%$
    
    Total carbon intensity: ${ci}_{H2} = \ \frac{\left( {el}_{grid\_ ely} + el_{grid\_ aux} \right)\ ci_{grid}}{\left( el_{ren} + {el}_{grid\_ ely} \right)\ \eta_{ely}\ \ } = \frac{50.5\ GWh\ 100\ g/kWh}{550\ GWh\ 60\%} \approx 4.3\frac{g\ CO_{2}eq}{MJ}$
        
    
    
??? "CO~2~ source"
    ## CO~2~ source
    
    ### Eligibility for the e~ex\ use~ “credit”
    
    -   The carbon incorporated into the fuel can be counted as negative emissions if it would have otherwise been emitted as CO~2~ to the atmosphere and stems from air capture, biofuel, RCF or RFNBO production or combustion or an already emitting geological source. Until 2035, also fossil CO2 is eligible if taken into account in an effective carbon pricing system. [GHG.10](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q37](faq.md#Q37) [Q38](faq.md#Q38) [Q39](faq.md#Q39) [Q40](faq.md#Q40) [Q41](faq.md#Q41) [Q42](faq.md#Q42) [Q43](faq.md#Q43) [Q44](faq.md#Q44) [Q45](faq.md#Q45) [Q46](faq.md#Q46) \[Q-Annex3\]
    
    ### Example in this case study
    
    The CO~2~ comes from a biomass boiler.
    
    Emissions from CO~2~ capture and supply: $e_{bio\_ supply} = 3.6\frac{g\ CO_{2}eq}{kg\ CO_{2}}$
        
    
    
??? "Methanol production"
    ## Methanol production
    
    ### Example in this case study
    
    The inputs are supplied by the processes described above, the auxiliaries use grid electricity. We assume no additional non-biogenic GHG emissions in the process.
    
    Input of hydrogen: $meoh_{H2} = 1.2\frac{MJ_{H2}}{MJ_{MeOH}}$
    
    Input of CO~2~: $meoh_{CO2} = 0.075\ \frac{kg\ CO_{2}}{MJ_{MeOH}}$
    
    Input of electricity: $meoh_{el} = 0.05\ \frac{MJ_{el}}{MJ_{MeOH}}$
    
    Share of RFNBO in the output is $s_{RFNBO\_ MeOH} = \ 91\%$
    
    Conversion rate of CO~2~: $conv_{CO2} = 90\%$
    
    Total carbon intensity: ${ci}_{MeOH} = \ meoh_{h2}\ ci_{H2} + \frac{meoh_{co2}}{conv_{CO2}}\ ci_{co2} + meoh_{el}\ ci_{grid} \approx 6.8\frac{g\ CO_{2}eq}{MJ_{MeOH}}$
        
    
    
??? "Fuel transport"
    ## Fuel transport
    
    ### Emissions
    
    -   Emissions of transport should be allocated based on the emissions attributable to the RFNBO (generally by energy, mass or volume of the overall transported fuel). This includes empty return trips. [GHG.1](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q60](faq.md#Q60) 
    
    ### Example in this case study
    
    The ship is loaded with 80% of the methanol produced in this pathway and 20% fossil methanol. The return trip is empty. Transport emissions are calculated by dividing the overall emissions of both trips by the overall fuel transported and allocated by energy to all fuels.

    Emissions caused by transport: $e_{transp} = 1\frac{g\ CO_{2}eq}{MJ_{fuel\_ transported}}$
    
    Total carbon intensity: ${ci}_{MeOH\_ transported} = \ {ci}_{MeOH} + e_{transp} \approx 7.8\frac{g\ CO_{2}eq}{MJ_{MeOH\_ transported}}$
        
    
    
??? "Hydrogen and oxygen production"
    ## Hydrogen and oxygen production
    
    ### Allocation of emissions to products without energy content
    
    -   If oxygen is sold as a product, emissions can be allocated to it by economic value (average factory-gate value of the products over the last three years). [GHG.15](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q51](faq.md#Q51) 
    
    ### Example in this case study

    Mass ratio of oxygen to hydrogen: $m_{O2} = 8\frac{kg{\ O}_{2}}{kg\ H_{2}}$
    
    Average factory-gate price of hydrogen: $p_{H2} = 5\frac{€}{kg\ H_{2}}$
    
    Average factory-gate price of oxygen: $p_{O2} = 0.1\frac{€}{kg\ O_{2}}$
    
    Total emissions for electrolysis (in this case assumed to be only from electrolysis):$\ e_{ely\_ aux} = 0.5\frac{g\ CO_{2}eq}{MJ_{H2}}$
    
    Allocation of emissions to hydrogen: $alloc_{H2} = \ \frac{p_{H2}}{p_{O2}m_{O2} + p_{H2}} \approx 86\%$
    
    Emissions attributed to hydrogen: $e_{ely\_ H2} = e_{ely\_ aux}\ alloc_{H2} \approx 0.43\frac{g\ CO_{2}eq}{MJ\ H_{2}}$
        
    
    
??? "Use of waste heat"
    ## Use of waste heat
    
    ### Waste heat as rigid input
    
    -   If waste heat from another process is used as energy input, and the waste heat production cannot be increased and does not represent 10% of the economic value or more, it can be considered a rigid input with no emissions attributed to it. [GHG.4](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q47](faq.md#Q47) 
    
    ### Example in this case study
    
    The heat in the case study can be considered waste heat with no emissions.
    
??? "Final fuel production"
    ## Final fuel production
    
    ### Share of RFNBO in each output stream
    
    -   The share of RFNBO in all outputs should be equal. [RED II 30](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=uriserv:OJ.L_.2018.328.01.0082.01.ENG#030.002) \[Q-Annex2\][Q49](faq.md#Q49) [Q53](faq.md#Q53) [Q54](faq.md#Q54) 
    
    ### Share of overall RFNBO in the output
    
    -   If the additional hydrogen is an RFNBO and increases the heating value of the outputs, it also increases the share of RFNBO in the output. [Q55](faq.md#Q55) [Q59](faq.md#Q59) 
    
    ### Other sectors than transport
    
    -   According to the new RED, RFNBO terminology can also be used in other sectors. [RED II rev](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32023L2413) [Q10](faq.md#Q10) 
    
    ### Example in this case study
    
    For illustration purposes, the methanol-to-synfuels process is modified and simplified to only produce diesel and kerosene and only use methanol, hydrogen and heat as inputs. In this example, we assume that the heat is not contributing to the heating value of the fuel.

    Energy share of diesel in output: $s_{diesel} = 44\%$
    
    Energy share of kerosene in output: $s_{kerosene} = 56\%$
    
    Input of methanol: $fuel_{MeOH} = 1.1\frac{MJ\ MeOH}{MJ\ fuel}$
    
    Input of hydrogen: $fuel_{H2} = 0.1\frac{MJ\ H_{2}}{MJ\ fuel}$
    
    Input of heat: $fuel_{heat} = 0.2\frac{MJ\ heat}{MJ\ fuel}$
    
    Share of RFNBO: $s_{RFNBO\_ fuels} = \ \frac{s_{RFNBO\_ MeOH}*{fuel}_{MeOH} + 1*\ {fuel}_{H2}}{{fuel}_{MeOH} + {fuel}_{H2}} \approx 92\%$
    
    Emissions attributed to all fuels:$\ {E = ci}_{fuels} = \ {fuel}_{MeOH}\ {ci}_{MeOH\_ transported} + {fuel}_{h2}\ ci_{H2} + {fuel}_{heat}\ ci_{heat} \approx 8.6\frac{g\ CO_{2}eq}{MJ\ fuel}$
    
    Emission reduction compared to the fossil fuel comparator: $Savings = \ \frac{E_{F} - E}{E_{F}} = \frac{94 - 8.6}{94} \approx 91\%$