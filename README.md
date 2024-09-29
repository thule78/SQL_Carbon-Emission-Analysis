# SQL_Carbon-Emission-Analysis
Data Source: Where Our Data Comes From Our dataset is compiled from publicly available data from nature.com and encompasses the product carbon footprints (PCF) for various companies. PCFs represent the greenhouse gas emissions associated with specific products, quantified in CO2 (carbon dioxide equivalent).

### table review
----
SELECT * FROM product_emissions LIMIT 50;
----
 
| id            | company_id | country_id | industry_group_id | year | product_name                                                    | weight_kg | carbon_footprint_pcf | upstream_percent_total_pcf                       | operations_percent_total_pcf                     | downstream_percent_total_pcf                     | 
| ------------: | ---------: | ---------: | ----------------: | ---: | --------------------------------------------------------------: | --------: | -------------------: | -----------------------------------------------: | -----------------------------------------------: | -----------------------------------------------: | 
| 10056-1-2014  | 82         | 28         | 2                 | 2014 | Frosted Flakes(R) Cereal                                        | 0.7485    | 2                    | 57.50                                            | 30.00                                            | 12.50                                            | 
| 10056-1-2015  | 82         | 28         | 15                | 2015 | "Frosted Flakes, 23 oz, produced in Lancaster, PA (one carton)" | 0.7485    | 2                    | 57.50                                            | 30.00                                            | 12.50                                            | 
| 10222-1-2013  | 83         | 28         | 8                 | 2013 | Office Chair                                                    | 20.68     | 73                   | 80.63                                            | 17.36                                            | 2.01                                             | 
| 10261-1-2017  | 14         | 16         | 25                | 2017 | Multifunction Printers                                          | 110       | 1488                 | 30.65                                            | 5.51                                             | 63.84                                            | 
| 10261-2-2017  | 14         | 16         | 25                | 2017 | Multifunction Printers                                          | 110       | 1818                 | 25.08                                            | 4.51                                             | 70.41                                            | 
| 10261-3-2017  | 14         | 16         | 25                | 2017 | Multifunction Printers                                          | 110       | 2274                 | 20.05                                            | 3.61                                             | 76.34                                            | 
| 10324-1-2016  | 15         | 16         | 19                | 2016 | KURALON  fiber                                                  | 1500      | 10000                | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10418-1-2013  | 84         | 9          | 19                | 2013 | Portland Cement                                                 | 1000      | 1102                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-10-2014 | 85         | 28         | 11                | 2014 | Regular Straight 505® Jeans – Steel (Water                      | 0.7665    | 15                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-10-2015 | 85         | 28         | 6                 | 2015 | Regular Straight 505® Jeans – Steel (Water                      | 0.7665    | 15                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-10-2016 | 85         | 28         | 11                | 2016 | Regular Straight 505® Jeans – Steel (Water                      | 0.7665    | 15                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-11-2014 | 85         | 28         | 11                | 2014 | 501® Original Jeans – Rinse Run                                 | 0.997     | 15                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-11-2015 | 85         | 28         | 6                 | 2015 | 501® Original Jeans – Rinse Run                                 | 0.997     | 16                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-1-2014  | 85         | 28         | 11                | 2014 | 501® Original Jeans – Dark Stonewash                            | 0.997     | 16                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-1-2015  | 85         | 28         | 6                 | 2015 | 501® Original Jeans – Dark Stonewash                            | 0.997     | 16                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-1-2016  | 85         | 28         | 11                | 2016 | 501® Original Jeans – Dark Stonewash                            | 0.997     | 16                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-2-2014  | 85         | 28         | 11                | 2014 | Slim Straight 514™ Jeans – Indigo Wash                          | 0.68      | 9                    | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-2-2015  | 85         | 28         | 6                 | 2015 | Slim Straight 514™ Jeans – Indigo Wash                          | 0.68      | 9                    | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-2-2016  | 85         | 28         | 11                | 2016 | Slim Straight 514™ Jeans – Indigo Wash                          | 0.88      | 9                    | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-3-2014  | 85         | 28         | 11                | 2014 | Slim Straight 514™ Jeans – Rigid Tank                           | 0.68      | 8                    | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-3-2015  | 85         | 28         | 6                 | 2015 | Slim Straight 514™ Jeans – Rigid Tank                           | 0.68      | 8                    | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-3-2016  | 85         | 28         | 11                | 2016 | Slim Straight 514™ Jeans – Rigid Tank                           | 0.88      | 8                    | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-4-2014  | 85         | 28         | 11                | 2014 | 501® Original Jeans – Light Stonewash                           | 0.997     | 15                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-4-2015  | 85         | 28         | 6                 | 2015 | 501® Original Jeans – Light Stonewash                           | 0.997     | 15                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-5-2014  | 85         | 28         | 11                | 2014 | 501® Original Jeans – Medium Stonewash                          | 0.997     | 16                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-5-2015  | 85         | 28         | 6                 | 2015 | 501® Original Jeans – Medium Stonewash                          | 0.997     | 16                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-6-2014  | 85         | 28         | 11                | 2014 | Slim Straight 514™ Jeans – Tumbled Rigid                        | 0.68      | 16                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-6-2015  | 85         | 28         | 6                 | 2015 | Slim Straight 514™ Jeans – Tumbled Rigid                        | 0.68      | 16                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-7-2014  | 85         | 28         | 11                | 2014 | Regular Straight 505® Jeans – Range (Water                      | 0.7665    | 16                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 1198-2-2014   | 1          | 28         | 24                | 2014 | USB software                                                    | 0.0085    | 2                    | 67.61                                            | 2.22                                             | 30.17                                            | 
| 10661-7-2015  | 85         | 28         | 6                 | 2015 | Regular Straight 505® Jeans – Range (Water                      | 0.7665    | 16                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-8-2014  | 85         | 28         | 11                | 2014 | Regular Straight 505® Jeans – Range                             | 0.7665    | 16                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-8-2015  | 85         | 28         | 6                 | 2015 | Regular Straight 505® Jeans – Range                             | 0.7665    | 16                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-9-2014  | 85         | 28         | 11                | 2014 | Regular Straight 505® Jeans – House Cat                         | 0.7665    | 15                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10661-9-2015  | 85         | 28         | 6                 | 2015 | Regular Straight 505® Jeans – House Cat                         | 0.7665    | 16                   | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10666-10-2014 | 16         | 28         | 25                | 2014 | MS315DN - Mono Laser Printer                                    | 16.03449  | 1616                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10666-11-2014 | 16         | 28         | 25                | 2014 | MS410DN - Mono Laser Printer                                    | 15.898413 | 1523                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10666-1-2014  | 16         | 28         | 25                | 2014 | CX310DN - Color Laser Printer                                   | 31.365912 | 2358                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10666-12-2014 | 16         | 28         | 25                | 2014 | MS415DN - Mono Laser Printer                                    | 16.03449  | 1525                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10666-13-2014 | 16         | 28         | 25                | 2014 | MS510DN - Mono Laser Printer                                    | 16.66952  | 1618                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10666-14-2014 | 16         | 28         | 25                | 2014 | MS610DE - Mono Laser Printer                                    | 18.37049  | 1978                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10666-15-2014 | 16         | 28         | 25                | 2014 | MS610DN - Mono Laser Printer                                    | 17.576704 | 1958                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10666-16-2014 | 16         | 28         | 25                | 2014 | MS810DE - Mono Laser Printer                                    | 27.4877   | 2107                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10666-17-2014 | 16         | 28         | 25                | 2014 | MS810DN - Mono Laser Printer                                    | 27.44234  | 2005                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10666-18-2014 | 16         | 28         | 25                | 2014 | MS811DN - Mono Laser Printer                                    | 27.44234  | 2388                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10666-19-2014 | 16         | 28         | 25                | 2014 | MS812DE - Mono Laser Printer                                    | 27.75985  | 2744                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10666-20-2014 | 16         | 28         | 25                | 2014 | MS812DN - Mono Laser Printer                                    | 27.44234  | 2747                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10666-21-2014 | 16         | 28         | 25                | 2014 | MX310DN - Mono Laser Printer                                    | 22.45282  | 1140                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10666-2-2014  | 16         | 28         | 25                | 2014 | CX410DE - Color Laser Printer                                   | 31.365912 | 3236                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 
| 10666-22-2014 | 16         | 28         | 25                | 2014 | MX410DE - Mono Laser Printer                                    | 23.019813 | 1499                 | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | N/a (product with insufficient stage-level data) | 

### What are the industries with the highest contribution to carbon emissions?
----
SELECT ig.industry_group AS industry, pcf_table.avg_pcf
FROM(
    SELECT ROUND(AVG(carbon_footprint_pcf)) AS avg_pcf, industry_group_id
    FROM product_emissions
    GROUP BY industry_group_id
) AS pcf_table
JOIN industry_groups AS ig
ON ig.id = pcf_table.industry_group_id
ORDER BY pcf_table.avg_pcf DESC
LIMIT 10;
----

| industry                                         | avg_pcf | 
| -----------------------------------------------: | ------: | 
| Electrical Equipment and Machinery               | 891051  | 
| Automobiles & Components                         | 35373   | 
| "Pharmaceuticals, Biotechnology & Life Sciences" | 24162   | 
| Capital Goods                                    | 7392    | 
| Materials                                        | 3209    | 
| "Mining - Iron, Aluminum, Other Metals"          | 2727    | 
| Energy                                           | 2155    | 
| Chemicals                                        | 1949    | 
| Media                                            | 1534    | 
| Software & Services                              | 1369    | 

### Which products contribute the most to carbon emissions?
----
SELECT product_name, ROUND(AVG(carbon_footprint_pcf)) AS emission
FROM product_emissions
GROUP BY product_name
ORDER BY emission DESC
LIMIT 10;
----

| product_name                                                                                                                       | emission | 
| ---------------------------------------------------------------------------------------------------------------------------------: | -------: | 
| Wind Turbine G128 5 Megawats                                                                                                       | 3718044  | 
| Wind Turbine G132 5 Megawats                                                                                                       | 3276187  | 
| Wind Turbine G114 2 Megawats                                                                                                       | 1532608  | 
| Wind Turbine G90 2 Megawats                                                                                                        | 1251625  | 
| Land Cruiser Prado. FJ Cruiser. Dyna trucks. Toyoace.IMV def unit.                                                                 | 191687   | 
| Retaining wall structure with a main wall (sheet pile): 136 tonnes of steel sheet piles and 4 tonnes of tierods per 100 meter wall | 167000   | 
| TCDE                                                                                                                               | 99075    | 
| Mercedes-Benz GLE (GLE 500 4MATIC)                                                                                                 | 91000    | 
| Mercedes-Benz S-Class (S 500)                                                                                                      | 85000    | 
| Mercedes-Benz SL (SL 350)                                                                                                          | 72000    | 

### What are the industry groups of these products?

----
SELECT pe.product_name, i.industry_group,ROUND(AVG(pe.carbon_footprint_pcf)) AS emission
FROM product_emissions AS pe
JOIN industry_groups AS i
ON pe.industry_group_id = i.id
GROUP BY pe.product_name
ORDER BY emission DESC
LIMIT 10;
----
| product_name                                                                                                                       | industry_group                     | emission | 
| ---------------------------------------------------------------------------------------------------------------------------------: | ---------------------------------: | -------: | 
| Wind Turbine G128 5 Megawats                                                                                                       | Electrical Equipment and Machinery | 3718044  | 
| Wind Turbine G132 5 Megawats                                                                                                       | Electrical Equipment and Machinery | 3276187  | 
| Wind Turbine G114 2 Megawats                                                                                                       | Electrical Equipment and Machinery | 1532608  | 
| Wind Turbine G90 2 Megawats                                                                                                        | Electrical Equipment and Machinery | 1251625  | 
| Land Cruiser Prado. FJ Cruiser. Dyna trucks. Toyoace.IMV def unit.                                                                 | Automobiles & Components           | 191687   | 
| Retaining wall structure with a main wall (sheet pile): 136 tonnes of steel sheet piles and 4 tonnes of tierods per 100 meter wall | Materials                          | 167000   | 
| TCDE                                                                                                                               | Materials                          | 99075    | 
| Mercedes-Benz GLE (GLE 500 4MATIC)                                                                                                 | Automobiles & Components           | 91000    | 
| Mercedes-Benz S-Class (S 500)                                                                                                      | Automobiles & Components           | 85000    | 
| Mercedes-Benz SL (SL 350)                                                                                                          | Automobiles & Components           | 72000    | 

### What are the companies with the highest contribution to carbon emissions?
----
SELECT c.company_name,ROUND(AVG(pe.carbon_footprint_pcf)) AS emission
FROM product_emissions AS pe
JOIN companies AS c
ON pe.company_id = c.id
GROUP BY c.company_name
ORDER BY emission DESC
LIMIT 10;
----
| company_name                           | emission | 
| -------------------------------------: | -------: | 
| "Gamesa Corporación Tecnológica, S.A." | 2444616  | 
| "Hino Motors, Ltd."                    | 191687   | 
| Arcelor Mittal                         | 83504    | 
| Weg S/A                                | 53552    | 
| Daimler AG                             | 43089    | 
| General Motors Company                 | 34252    | 
| Volkswagen AG                          | 26238    | 
| Waters Corporation                     | 24162    | 
| "Daikin Industries, Ltd."              | 17600    | 
| CJ Cheiljedang                         | 15803    | 

### What are the countries with the highest contribution to carbon emissions?
----
SELECT c.country_name,ROUND(AVG(pe.carbon_footprint_pcf)) AS emission
FROM product_emissions AS pe
JOIN countries AS c
ON pe.company_id = c.id
GROUP BY c.country_name
ORDER BY emission DESC
LIMIT 10;
----
| country_name | emission | 
| -----------: | -------: | 
| Germany      | 2444616  | 
| Greece       | 191687   | 
| Colombia     | 17600    | 
| Lithuania    | 13251    | 
| Italy        | 10000    | 
| India        | 9328     | 
| South Africa | 3551     | 
| China        | 3500     | 
| Canada       | 3025     | 
| Belgium      | 2344     | 

### What is the trend of carbon footprints (PCFs) over the years?
----
SELECT year,ROUND(AVG(pe.carbon_footprint_pcf)) AS emission
FROM product_emissions AS pe
GROUP BY year
ORDER BY year;
----
| year | emission | 
| ---: | -------: | 
| 2013 | 2399     | 
| 2014 | 2458     | 
| 2015 | 43189    | 
| 2016 | 6892     | 
| 2017 | 4051     | 

### Which industry groups has demonstrated the most notable decrease in carbon footprints (PCFs) over time? (intermediate level, without using CTE)
----
SELECT c.industry_name, c.year, c.emissions AS current_pcf, p.emissions AS previous_pcf,
	(c.emissions - p.emissions) AS decrease_pcf
FROM
	(SELECT pe.industry_group_id AS industry_id, pe.year AS year , 
		i.industry_group AS industry_name, SUM(pe.carbon_footprint_pcf) AS emissions
	FROM product_emissions AS pe
	JOIN industry_groups AS i
	ON i.id = pe.industry_group_id
	GROUP BY i.industry_group, pe.year) AS c
LEFT JOIN
	(SELECT pe.industry_group_id AS industry_id, pe.year AS year , 
		i.industry_group AS industry_name, SUM(pe.carbon_footprint_pcf) AS emissions
	FROM product_emissions AS pe
	JOIN industry_groups AS i
	ON i.id = pe.industry_group_id
	GROUP BY i.industry_group, pe.year) AS p
ON c.industry_id = p.industry_id AND c.year = p.year + 1
WHERE p.emissions IS NOT NULL
ORDER BY decrease_pcf;
----
| industry_name                                    | year | current_pcf | previous_pcf | decrease_pcf | 
| -----------------------------------------------: | ---: | ----------: | -----------: | -----------: | 
| Materials                                        | 2014 | 75678       | 200513       | -124835      | 
| Technology Hardware & Equipment                  | 2016 | 1566        | 106157       | -104591      | 
| "Food, Beverage & Tobacco"                       | 2017 | 3162        | 100289       | -97127       | 
| Capital Goods                                    | 2015 | 3505        | 93699        | -90194       | 
| Technology Hardware & Equipment                  | 2015 | 106157      | 167361       | -61204       | 
| Software & Services                              | 2017 | 690         | 22846        | -22156       | 
| Media                                            | 2015 | 1919        | 9645         | -7726        | 
| "Food, Beverage & Tobacco"                       | 2015 | 0           | 2685         | -2685        | 
| "Food, Beverage & Tobacco"                       | 2014 | 2685        | 4995         | -2310        | 
| Commercial & Professional Services               | 2017 | 741         | 2890         | -2149        | 
| Food & Staples Retailing                         | 2016 | 2           | 706          | -704         | 
| Commercial & Professional Services               | 2014 | 477         | 1157         | -680         | 
| Media                                            | 2016 | 1808        | 1919         | -111         | 
| Food & Staples Retailing                         | 2015 | 706         | 773          | -67          | 
| Software & Services                              | 2016 | 22846       | 22856        | -10          | 
| Retailing                                        | 2015 | 11          | 19           | -8           | 
| Telecommunication Services                       | 2015 | 183         | 183          | 0            | 
| Media                                            | 2014 | 9645        | 9645         | 0            | 
| Telecommunication Services                       | 2014 | 183         | 52           | 131          | 
| Software & Services                              | 2014 | 146         | 6            | 140          | 
| Consumer Durables & Apparel                      | 2014 | 3280        | 2867         | 413          | 
| Capital Goods                                    | 2016 | 6369        | 3505         | 2864         | 
| "Pharmaceuticals, Biotechnology & Life Sciences" | 2014 | 40215       | 32271        | 7944         | 
| Software & Services                              | 2015 | 22856       | 146          | 22710        | 
| Technology Hardware & Equipment                  | 2017 | 27592       | 1566         | 26026        | 
| Capital Goods                                    | 2014 | 93699       | 60190        | 33509        | 
| Capital Goods                                    | 2017 | 94949       | 6369         | 88580        | 
| Automobiles & Components                         | 2014 | 230015      | 130189       | 99826        | 
| "Food, Beverage & Tobacco"                       | 2016 | 100289      | 0            | 100289       | 
| Technology Hardware & Equipment                  | 2014 | 167361      | 61100        | 106261       | 
| Materials                                        | 2017 | 213137      | 88267        | 124870       | 
| Automobiles & Components                         | 2015 | 817227      | 230015       | 587212       | 
| Automobiles & Components                         | 2016 | 1404833     | 817227       | 587606       | 
