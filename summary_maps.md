## Functions and summary
- df.column_name.mean()
- df.column_name.median()
- df.column_name.unique()
- df.column_name.value_counts()
- df.column_A + '-' + df.column_B


### Maps (don't modify the original data)

- var_mean = df.numerical_column.mean()
- df.numerical_column.map(lambda p: p - var_mean)
> --- 
- var_mean = df.numerical-column.mean()
- df.numerical_column - var_mean
> ---
```python
n_trop = reviews.description.map(lambda desc: "tropical" in desc).sum()
n_fruity = reviews.description.map(lambda desc: "fruity" in desc).sum()
descriptor_counts = pd.Series([n_trop, n_fruity], index=['tropical', 'fruity'])
```
> ---

### Aply (don't modify the original data)

```python
def remean_points(row):
    row.points = row.points - review_points_mean
    return row

reviews.apply(remean_points, axis='columns')
```
> ---
```python
def stars(row):
    if row.country == 'Canada':
        return 3
    elif row.points >= 95:
        return 3
    elif row.points >= 85:
        return 2
    else:
        return 1

star_ratings = reviews.apply(stars, axis='columns')
```
