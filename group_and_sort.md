## Group and Sort

### Group
```python
# The same as value_counts()
df.groupby('some_colum').some_column.count()
```
```python
# we can use any summary functions (min, max, mean etc..)
df.groupby('some_column').other_column.min()
```
```python
df.groupby('some_column').apply(lambda df_var: df_var.title.iloc[0])
```
```python
# group 2 columns
df.groupby(['column_A', 'column_B'].apply(lambda df_var.loc[df_var.column_c.idmax()]))

```
```python
# we can use more than one summary function with agg()
df.groupby(['column_A']).column_B.agg([len, min, max])
```
```python
# multi-index
column_A_df = df.groupby(['column_A', 'column_B']).column_C.agg([len])
```
```python
# converting back a regular index
column_A_df.df.reset_index()
```
### Sort
```python
# sorting by values ignoring index
column_A_df = column_A_df.reset_index()
column_A_df.sort_values(by='column_q')

column_A_df.sort_values(by='column_q', ascending=False)
```
```python
# sort by index
column_A_df.sort_index()
```
```python
# sort by two columns
column_A_df.sort_values(by=['column_q', 'column_w'])
```

### Do the same and examples
```python
reviews_written = reviews.groupby('taster_twitter_handle').size()
reviews_written = reviews.groupby('taster_twitter_handle').taster_twitter_handle.count()
```
```python
# sorted by lowest price & max points
best_rating_per_price = reviews.groupby('price')['points'].max().sort_index()
```
```python
# index 'variety' values min and max
price_extremes = reviews.groupby('variety').price.agg([min, max])
```
```python
# variety sorted desc by minimun price, then maximum price
sorted_varieties = price_extremes.sort_values(by=['min', 'max'], ascending=False)
```
```python
# index 'taster_name' values is the average reviews score
reviewer_mean_ratings = reviews.groupby('taster_name')['points'].mean()
```
```python
# multi-index sort value desc of wine count
country_variety_counts = reviews.groupby(['country', 'variety']).size().sort_values(ascending=False)
```


