## Dataframe
> is a table. It contains an array of individual entries, each of which has a certain value. Each entry corresponds to a row (or record) and a column.
## Series
> is a sequence of data values. If a DataFrame is a table, a Series is a list.

## usually comands
- df = pd.DataFrame(dictionary)
- df.shape()
- df.head(|int)
- df.tail()
- df.describe()
- df.to_csv('name.csv')
- df.column-name // df['column-name']
- df.['column-name'][index]
- df.set_index('column_name')


## Conditional
- df.column_name == 'valueX'
- df.loc[df.column_name == 'valueX']
- df.loc[(df.column_name == 'valueX') & (df.other_column_name >= n)]
- df.loc[(df.column_name == 'valueX') | (df.other_column_name >= n)]
- df.loc[df.column_name.isin(['column_name', 'other_column_name'])]
- df.loc[df.column_name.notnull()]

## Assigning data
- df['column_name'] = 'something'
- df['column_name']= range(len(df), 0, -1)

## Types
- df.dtype
- df.column.dtype
- df.column.astype('float64')
- df.index.dtype

## Missing data
- df[pd.isnull(df.column)]
- df[df.column.isnull()]
- pd.isnull(df.column)
- df.column.fillna('something')
- df.column.replace("old_value", 'new_value')

## Renaming
- df.rename(columns={'old_name_column': 'new_name_column'})
- df.rename(index={0: 'first_index', 1:'second_index'})
- df.rename_axis('name_for_indexCol', axis='rows').rename_axis('name_for_rowCols', axis='columns')


## Combining
```python
# dfs need to have the same fields(columns)
one_df = p.read_csv('../one.csv')
second_df = p.read_csv('../second.csv')
pd.concat([one_df, second_df])
```

```python
left = one_df.set_index(['column_A', 'column_B'])
right = second_df.set_index(['column_A', 'column_B'])
left.join, (right, lsuffix='_ONE', rsuffix='_SECOND')
```




