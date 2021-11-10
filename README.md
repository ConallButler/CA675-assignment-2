# CA675-assignment-2

Overview of transformation steps;

1.	Filter cases data by case type; create different relation for each case type then do a join by (date, country) to get the three case types in a single relation
2.	Union of countries field from vaccine csv and case numbers csv --> get distinct countries
3.	Input continent for each country manually, generate csv with schema (country, continent)
4.	Join cases csv by country each entry now has a continent 
5.	Group by (date, continent); relation will have schema [(date, continent),{(country, confirmed_cases, deaths, recovered)}]
6.	For each (date, continent) sum {(deaths)} as deaths
7.	Repeat for confimed_cases and recovered
8.	So we now have (date, continent, confirmed_cases, deaths, recovered) for each (date, continent) pair
9.	Do steps 4-8 for vaccination numbers/population
10.	We now also have (date, continent, partially vaccinated, Fully_vaccinated, Population) for each (date, continent) pair
11.	Left outer join Continent_Cases with Continent_Vaccination_populatiuon by (date, continent)
12.	We now have [(date, continent)], confirmed_cases, deaths, recovered, Continent_partially vaccinated, Continent_Fully_Vaccinated
13.	To get separate CSVs; filter by continent the store to CSV
