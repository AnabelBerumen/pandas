 ## Uses of loc and iloc
> They are row-first, column-second.
### iloc   *selected by position*
> where the first element of the range is included and the last one excluded. So 0:10 will select entries 0,...,9
###### *First row of data*
- df.iloc[index_row] 
###### *Get column*
- df.iloc[:,0]
###### *Get data for a range of column*
- df.iloc[:3, 0]
- df.iloc[1:3,0]
- df.iloc[[0,1,2],0]
- df.iloc[3:5, 0:2]
- df.iloc[[1, 2, 4], [0, 2]]
###### *Last n values of the dataset*
- df.iloc[-5:]


### loc   *selected by label*
>  indexes inclusively. So 0:10 will select entries 0,...,10
###### *First entry in df*
- df.loc[0, 'column_name']
###### *[all] of [n columns-name]*
- df.loc[:,['column_one', 'column_four', 'column_n']]
###### *geting a cross section*
- df.loc[name_index_col[0]]
###### *slicing*
- df.loc['name_index': 'name_index',['column_A', 'column_B']]
###### *reduction in the dimension of the return*
- df.loc['name_index', ['column_A','column_B']]
###### *Geting a scalar*
- df.loc[name_index_col[0], 'column_A']   
- df.at[name_index_col[0], 'column_A']
###### *Geting mixed rows*
- df.loc[[1,3,6,7,8]]


### do the same
- first_descriptions = reviews.loc[:9, 'description']
- first_descriptions = reviews.description.iloc[:10]
> ---
- first_description = reviews.loc[0,'description']
- first_description = reviews.description.iloc[0]
> ---
- df = reviews.loc[:99, ['country', 'variety']]
- 
- cols = ['country', 'variety']
- df = reviews.loc[:99, cols]
-
- cols_idx = [0, 11]
- df = reviews.loc[:99, cols]
- > ---
- top_oceania_wines = reviews.loc[((reviews['country'] =='New Zealand') | (reviews['country'] =='Australia'))& (reviews.points >= 95)]
- top_oceania_wines = reviews.loc[
(reviews.country.isin(['Australia', 'New Zealand']))
    & (reviews.points >= 95)
]
