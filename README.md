
## Primary Author & Maintainer:
1. [Thanh (Randy) Bui](https://github.com/thanh8ui)


---


## Dataset Description:
**Dataset Title:** Electric Vehicle Population Data  
**Format:** CSV  
**Source:** [Data.gov - WA State Department of Licensing](https://catalog.data.gov/dataset/electric-vehicle-population-data)  


 Field | Type | Description |
|-------|------|-------------|
| **VIN (1-10)** | string | First 10 characters of the Vehicle Identification Number; uniquely identifies the vehicle |
| **County** | string | County of registration |
| **City** | string | City of registration |
| **State** | string | Always “WA” |
| **Postal Code** | float | ZIP code of the registration address |
| **Model Year** | int | Model year of the vehicle |
| **Make** | string | Manufacturer (e.g., Tesla, Nissan) |
| **Model** | string | Model name |
| **Electric Vehicle Type** | string | “BEV” (Battery EV) or “PHEV” (Plug-in Hybrid) |
| **Clean Alternative Fuel** | string | CAFV incentive eligibility |
| **Electric Range** | float | EPA-estimated all-electric range (mi) |
| **Base MSRP** | float | Manufacturer’s Suggested Retail Price (USD) |
| **Legislative District** | float | WA State legislative district |
| **DOL Vehicle ID** | int | Unique ID from WA Dept. of Licensing |
| **Vehicle Location** | string | Latitude/longitude of the registration address |
| **Electric Utility** | string | Utility provider for the address |
| **2020 Census Tract** | float | Census tract for geospatial analysis |


**Rows:** ≈ 235,000+ | **Columns:** 17  
**Source:** Washington State Dept. of Licensing – [Electric Vehicle Population Data](https://catalog.data.gov/dataset/electric-vehicle-population-data)


I chose the Electric Vehicle Population Data dataset. It was published by the Washington State Department of Licensing, and it provides detailed information on registered electric vehicles in Washington State. 
This data captures a snapshot of EV population that includes one row per vehicle, which totals out of an approximate 159,467 entries, spanning 17 columns total. This data is public and is formatted such as CSV and JSON. Each row represents an individual record of the vehicle and the columns provide various attributes related to that vehicle. 
These include identifying and geographic details such as the first 10 characters of the Vehicle Identification Number (VIN), city, county, state (always “WA”), postal code, and census tract. Vehicle-specific details are also included, such as the model year, make (e.g., TESLA, NISSAN), model name, and electric vehicle type—either Battery Electric Vehicle (BEV) or Plug-in Hybrid Electric Vehicle (PHEV). Additionally, the dataset includes whether the vehicle qualifies as a Clean Alternative Fuel Vehicle (CAFV), its electric driving range in miles, and its base MSRP (Manufacturer’s Suggested Retail Price).
Policy-relevant identifiers are included, such as the Washington State legislative district where the vehicle is registered and the DOL vehicle ID number. The dataset also contains a "Vehicle Location" field with spatial coordinates, showing the latitude and longitude of the registration address, as well as the electric utility provider serving that location. This collection of information allows researchers, policymakers, and planners to analyze the geographic distribution, market penetration, and infrastructure needs related to electric vehicles across the state.
Overall, the dataset provides a comprehensive view of the EV landscape in Washington, supporting both environmental research and infrastructure planning by offering granular and geographically referenced information on every registered EV in the state.








---


## Project Questions:


### Question 1: How are electric vehicle (EV) registrations distributed across different counties in Washington State, and what geographic patterns emerge?
**Importance:** This question is important because it highlights regional adoption trends, revealing which areas are leading or lagging in EV adoption. Understanding this distribution has economic implications, such as guiding investment in charging infrastructure and influencing transportation planning. It is also socially relevant as it can expose disparities in access to clean transportation options. Additionally, this geographic analysis supports environmental policy development by identifying where incentives or educational campaigns may be most needed to encourage EV use. This question ties directly to the dataset through columns such as County, City, and Vehicle Location, allowing for spatial mapping and regional comparison.




### 2. : What is the trend in electric vehicle adoption by model year, and which manufacturers have contributed the most to this growth?
**Importance:** This question is important because it reveals how EV adoption has accelerated (or slowed) over time by model year, shedding light on consumer willingness to embrace newer electric technologies. Understanding these temporal trends has economic implications—planners and utilities can better time investments in charging infrastructure and grid upgrades to match waves of new registrations. It is also socially relevant, as surges in recent model years may reflect shifting public attitudes, policy incentives, or financing options, while stagnant years could signal barriers that need addressing. Additionally, identifying which manufacturers have driven the most growth informs competitive and policy decisions, such as tailoring rebate programs or supporting emerging brands to diversify the market. This question ties directly to the dataset through the Model Year and Make columns, enabling clear year‑over‑year trend analysis and manufacturer‐level contribution breakdowns.








---


## Data Manipulations:
### Question 1:
![Dashboard preview](https://snipboard.io/Sdcnhb.jpg)
 
Normalizing EV registrations by population—expressing them as the number of electric vehicles per 1,000 residents—ensures that larger counties don’t automatically dominate the rankings simply because they have more people. This per-capita approach reveals true adoption intensity: for example, a small county with 50 EVs and 5,000 residents (10 EVs per 1,000) is actually outpacing a much larger county with 500 EVs and 200,000 residents (2.5 EVs per 1,000). Framing the metric per 1,000 people also keeps the results readable, avoiding hard-to-interpret “0.00x” fractions. In short, by using EVs per 1,000 residents, you gain a fair, directly comparable view of adoption that highlights which counties are genuinely at the forefront of the electric-vehicle transition.


### Question 2:


When it comes to the manipulations of the data set, there were quite a few. For the data visualization of EV adoption over time, one of the important actions I used was to count the distinct number of VIN numbers, then grouping how many distinct vin numbers there were by each year. The purpose of this was to be able to count how many electric vehicles were adopted each year, using the VIN number as the primary key to identify new cars. I also filtered the color of the line depending on the count distinct of VIN numbers, so that it was easier to differentiate how much different each year was. Next, for the visualization of EV adoption by company, I used the same calculation of count distinct but instead, grouped by the brand. The reason for this was to see what companies are helping EV adoption the most, and the least, and by using count distinct, I made sure I'm not double counting any cars. 






---


## Analysis and Results:


### Question 1 Analysis:
![County-level EV bar chart](https://snipboard.io/ynIe1g.jpg)


![EV trend line chart](https://snipboard.io/2aOSQ6.jpg)



Question 1 Analysis: The per‐capita view of EV registrations in Washington clearly shows that counties with active incentive programs lead the state in EV owners. Jefferson and King counties both received Zero‐Emissions Access grants through Washington State’s ZAP program, Snohomish County offers up to $50 back on residential Level 2 charger installations, Benton PUD rebates customers who buy or lease a new EV, Clark Public Utilities provides up to $2,000 for income‐qualified used-EV purchases, and Spokane County makes a majority of its public charging ports free to use. These patterns underscore the power of targeted financial and infrastructure support: where grants, rebates, or publicly funded chargers exist, EV adoption reliably climbs. They also highlight untapped potential in Washington’s more remote counties—areas where extending charger rebates, grant funding, or small‐business incentives could catalyze new EV markets. Finally, the clustering of high per‐capita adoption along major transportation corridors and ferry routes confirms that placing fast chargers and outreach efforts in these strategic locations not only serves existing EV drivers but also helps build the broader network effects needed to spur even wider adoption.


### Question 2 Analysis:
![EV trend and manufacturer dashboard](https://snipboard.io/aENOAm.jpg)

Tesla’s lead in total EV registrations reflects early market entry and strong initial growth, but the leveling of its recent trendline suggests that its dominance is now being challenged by competitors scaling aggressively. This may indicate market maturation or the need for product refresh cycles to sustain momentum.




Ford’s rapid growth after 2020 signals a successful late entry strategy, likely driven by appealing EV offerings, mass-market availability, and manufacturing scale. If this trajectory continues, Ford could become the mainstream EV volume leader in coming years.




Volvo’s consistent rise and solid cumulative adoption numbers suggest a steady, long-term commitment to electrification, which may be resonating with environmentally conscious or safety-driven buyers in the premium mid-market.




Rivian’s sharp uptick post-2021 indicates successful entry into a specialized niche, such as electric trucks and SUVs for outdoor and lifestyle consumers. Its fast climb reflects effective product-market fit and marketing, but its long-term sustainability will depend on production and service infrastructure.




Companies that began EV adoption earlier, like Tesla and Volvo, show both higher cumulative totals and more stable annual adoption curves, suggesting that early investment in EV infrastructure and branding pays off over time with sustained market presence.




Lincoln’s minimal adoption and stagnant trendline highlights limited EV investment or late market entry, signaling potential brand risk as EV expectations rise among consumers.




The EV market is entering a new phase, where earlier leaders retain volume advantage but are no longer growing at the fastest rate. Instead, growth leadership is shifting to newer entrants and legacy automakers that have recently prioritized electrification at scale.




Split: Total Registrations Insights (Top Bar Chart)
Tesla dominates in overall EV count, followed by Ford and Volvo, both of which are now catching up in terms of recent growth.




Brands with very low totals, like Lincoln and Mitsubishi, likely lack competitive EV models or consumer traction.




Split: Growth Over Time Insights (Line Chart)
Ford leads recent-year growth, suggesting rising consumer acceptance of its newer EV models.




Early entrants like Tesla and Volvo show consistent adoption year over year, reinforcing the value of being first to market.




---


## Tableau Packaged Workbook:
The Tableau Packaged Workbook (.twbx) containing the visualizations and dashboards described above has been uploaded to the project GitHub repository.


-
