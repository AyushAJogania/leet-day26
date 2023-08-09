# leet-day26

# Big Countries

This SQL query retrieves the names, populations, and areas of countries that are considered big according to certain criteria. A country is considered big if it meets either of the following conditions:

1. The area of the country is at least three million square kilometers.
2. The population of the country is at least twenty-five million.

The query fetches the desired information from the `World` table, which contains data about various countries including their names, continents, areas, populations, and GDP values.

## SQL Query

```sql
SELECT name, population, area
FROM World
WHERE area >= 3000000 OR population >= 25000000;
```

## Explanation

The SQL query uses the `SELECT` statement to retrieve the `name`, `population`, and `area` columns from the `World` table. The `WHERE` clause specifies the conditions under which a country is considered big:

- `area >= 3000000`: This condition checks if the area of a country is greater than or equal to three million square kilometers.
- `population >= 25000000`: This condition checks if the population of a country is greater than or equal to twenty-five million.

The `OR` operator ensures that a country is considered big if it meets either of the conditions.

## Output

The output of the query will be a table with the columns `name`, `population`, and `area` containing information about the countries that satisfy the specified criteria for being big.

Please note that the result may vary based on the data in the `World` table.
