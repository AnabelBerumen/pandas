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
