
# df&ensp;&nbsp;&rarr;df.to_file
## create files
### read_files.
####  pd.read_csv
####  pd.read_excel
####  pd.read_html
### dataframe
#### series.to_frame() 
##### list&emsp;&emsp;|s_df
###### pd.Series([,,,..]).to_frame()
##### tuple&emsp;|s_df
###### pd.Series((,,,..)).to_frame()
##### dict.&nbsp;&emsp;|s_df
###### pd.Series({'key1':'val1',&emsp;'key2':'val2'}).to_frame()
##### np.arry|s_df
###### pd.Series(np.array([,,,..])).to_frame()
#### arry.to_frame() 
##### list&emsp;&emsp;|df
###### pd.DataFrame([,,,..],[,,,..] ,index=['','',..],columns=['','',..])
* single lists 
* index and columns both are needed
##### matrix&ensp;|df
###### pd.DataFrame(np.eye)
###### pd.DataFrame(np.identity)
###### pd.DataFrame(np.array([&nbsp;['','',''],['','',''],['','','']&nbsp;]))
##### dict&nbsp;&emsp;&ensp;|df
###### pd.DataFrame(dict({"colh":['','',..],&ensp;"colh":['','',..] }), index=['',''..]
* columns headers have already been provided 
* using dictionary key - value is the content in the column
##### np.arry|df
###### pd.DataFrame(np.array([['',''],['','']..]), index =['',''..] , columns =['','',..])
* nested lists
* columns headers and index are both needed
## df.to_file&emsp;
### df.to_csv('filename.csv')
### df.to_excel('filename.xlsx')
### df.to_html('filename.html')
#### html table :1 excel to or 2 df 
##### step 1 : 1.1 read_excel 1.2 create datainput
##### step 2 : convert datainput read_in as df
##### step 3 : html_table_1 = df1.to_html(index=False, border=1)\
##### step 4 : with open("table.html", "w", encoding="utf-8") as f:<br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;f.write(html_table_1)
# aggregation&emsp;
## statistics
### df.corr()
#### syntax & parameters 
###### syntax&emsp;&emsp;&nbsp;
* DataFrame.corr(method='pearson', min_periods=1, numeric_only=False) 
###### eg prior 
* original dataframe
* <table border="1"class="dataframe"><thead><trstyle="text-align:right;"><th>Height&emsp;</th><th>Weight&emsp;</th></tr></thead><tbody><tr><td>150</td><td>50</td></tr><tr><td>160</td><td>65</td></tr><tr><td>170</td><td>68</td></tr><tr><td>180</td><td>80</td></tr></tbody></table>
###### eg after 
* output dataframe
* <table border="1"class="dataframe"><thead><trstyle="text-align:right;"><th>Height</th><th>Weight</th></tr></thead><tbody><tr><td>1.000000</td><td><span style='background-color:cyan;color:grey;font-weight:bold'>0.973035</span></td></tr><tr><td><span style='background-color:cyan;color:grey;font-weight:bold'>0.973035</span></td><td>1.000000</td></tr></tbody></table>
###### parameters
* method: Correlation method (pearson, spearman, kendall), we get pearson correlation by default.
* min_periods: Minimum required matching values
* numeric_only: Includes only numeric columns if True
### df.describe().
### df['coln'].describe
### df.mean()
### df.median()
### df.mode()
### df.count()
## df.info() -type na entry
### df['coln'].info()
### concise summary of a DataFrame
### syantx
#### df.info(verbose=False)&emsp;&emsp;&emsp;&nbsp;
##### Setting verbose=True displays detailed information for all columns, while 
##### verbose=False provides a concise summary, omitting per-column details.
#### df.info(memory_usage=False)
##### True for basic memory details or 
##### 'deep' for a more detailed breakdown, including memory used by objects.
### importance
#### useful for gaining insight into dataframe -
#### understanding the <mark>structure of your dataset</mark> and 
#### identifying potential issues like <mark>missing values&emsp;</mark>.
##### how many entries for each column 
##### how many columns 
##### how many rows
##### how many null value 
##### how much memory it uses 
##### what are the data type for each column 
## df['age'].value_count() 
### useful for counting repeated values such as age how many people are at the age of 20
## df['age'].count()&emsp;&emsp;&ensp;&nbsp;
### simple calculation of the total instances
## <span style="background-color:cyan;color:magenta;font-weight:bold">df.transform() vs agg</span>
### comparison table
#### dataframe size&emsp; &rarr;&emsp;transform < &emsp; &emsp;| &emsp; &emsp;agg = 
##### overview
##### <table border="1" class="dataframe"><thead><tr style="text-align: left;"><th>aspects</th><th>df.agg()</th><th>df.transform()</th></tr></thead><tbody><tr><td>Purpose:</td><td>Performs aggregation — <br>reduces data to a smaller shape.</td><td>Performs broadcasting transformations — <br>returns an output with the same shape as the input.</td></tr><tr><td>Behavior:</td><td>The function is applied to each column (or row if axis=1) and <br>returns a scalar, Series, or DataFrame depending on the <br>aggregation.</td><td>The function is applied to each column individually and must return<br> a sequence of the same length as the group or DataFrame.</td></tr><tr><td>Use case:</td><td>Summarizing data, e.g., computing mean, sum, min, max, etc.</td><td>Group-wise normalization, filling values, or applying functions where <br>the result needs to align with the original index.</td></tr><tr><td>Shape:</td><td>Output is smaller than the input (reduced dimensions).</td><td>Output is same size as the input (broadcasted results).</td></tr></tbody></table>
###### comparison example df
###### ![Transform VS agg](./images/transormVSagg.png "System Diagram" )
### agg() | mostly df|
#### single column |df single function
##### df.agg('sum')
##### df['coln'].agg('sum')
#### single column|df multiple functions 
##### df.agg(['sum', 'min'])
##### df['coln'].agg(['sum', 'min'])
#### multiple columns multiple functions 
##### df.agg({'A': ['sum', 'min'], 'B': ['min', 'max']})
## df['coln'].transform(functionname)
### syntax 
#### df.trasform(lambda x:x*10)
#### df.transform(def)
#### df.groupby('x')['coln'].transform(function)
### use case
#### find outliers 
##### example:
##### &emsp; workflow of finding 10 outliers- find groupby mean- outliers  groupmean outlier
##### <div>&emsp;&emsp;cars['mean']=cars.groupby(['model_year','origin']).mpg.transform('mean').round(2)<br>&emsp;&emsp;&emsp;&emsp;&rarr;create a mean column<br>&emsp;&emsp;cars['mpg_outlier']=(cars.mpg-cars['mean']).round(2)<br>&emsp;&emsp;cars.loc[cars.mpg_outlier.abs()>10] <br>&emsp;&emsp;&emsp;&emsp;&rarr;create a new dataframe using filter condition absolute value</div>
#### substitute merge 
##### pd.merge(df_order ,df_ordertotal,on='id',how='left')
##### 
#### filter 
##### 
#### apply multiple functions to multiple columns simultaneously 
##### df.transform({'':func, lambda x：x*10})
##### example
##### 
## group by
### df.groupby('cat_coln')['val_coln'].mean() |single numeric column
### df.groupby('cat_coln').mean() |all numeric columns
### df.groupby('cat_coln').['val_coln'].agg(['mean','sum',..]) |mul agg 
### df.groupby('cat_coln').['val_coln'].apply()
# plot() for quick
## df.plot()
## df['coln'].plot()
### syntax parameters
#### example : df.plot(kind='scatter', x='Height', y='Weight', title='Height vs Weight', <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;xlabel='Height (cm)', ylabel='Weight (kg)', figsize=(8, 5))
#### kind=""
##### df.plot(kind='line')
##### df.plot(kind='bar')
##### df.plot(kind='barh')
##### df.plot(kind='hist')
##### df.plot(kind='scatter', x='col1', y='col2')
##### df.plot(kind='box')
##### df.plot(kind='kde')
##### df.plot(kind='pie')
##### df.plot(kind='area')
####  x	-data array|column_name x='colname' 
####  y -data array|column_name y='colname'
##### title	='sales over time'
##### xlabel='x'
##### ylabel='y'
##### color='blue'
##### figsiz=(&emsp;8&emsp;,&emsp;2&emsp;)
##### autopct='%1.1f%%'
### plt.legend
#### plt.legend(['A Label', 'B Label', 'C Label', 'D Label'], loc='center left', bbox_to_anchor=(1, 0.5))
## df.hist()
## best combination 
### pandas plot for quick analysis for self reference only 
### plt and seaborn -seaborn main focus plt adding details and formatting 
# nan missing values + duplicates.
## 👁️‍🗨️df['coln'].notna()&ensp;&nbsp;
### identify 
## 👁️‍🗨️df['coln'].isna()&emsp;&nbsp;
### identify 
## ✍df['coln'].fillna()&emsp;
### handle -replace it with a more sensible value 
### replace
#### =df['coln'].replace(np.nan,None)
###### timeseries 
* df.ffill() df.bfill()
###### fillna(mean)
* df['Cat'] = df['Cat'].fillna(df['Cate'].mode()[0])
###### fillna(dict)
* df.fillna(value={'A': 0, 'B': 1,'C': 'Missing'}) 
## ⛔df['coln'].dropna()
###### handle -drop
## <span style="background-color:cyan;color:magenta;font-weight:bold">💈df.interpolate()n</span>
### interpolate na 
####  fill missing values (NaN) in a DataFrame or Series using various interpolation techniques. 
* eg
* <div >time_index = pd.date_range('2023-01-01', periods=5, freq='D')data = [10, <span style="background-color:red;border:double white;padding:1px">&emsp;np.nan&emsp;</span>, 30,<span style="background-color:red;border:double white;padding:1px">&emsp;np.nan&emsp;</span>, 50]
* df = pd.DataFrame(data, index=time_index, columns=['Value'])
* df_interpolated = df.interpolate(method='time')
* print(df_interpolated)
* output:<br> 2023-01-01 <mark>|10.0|</mark> ,2023-01-02 <span style="background-color:red;border:double white;padding:1px">&emsp;20&emsp;</span> ,
* 2023-01-03 <mark>|30.0|</mark>, 2023-01-04 <span style="background-color:red;border:double white;padding:1px">&emsp;40&emsp;</span>,2023-01-05 <mark>|50.0|</mark></div>
## df['coln'].drop_duplicates(keep)<span style="font-size:25px;background-color:blue">⤫</span>
## df.duplicated(['coln1','coln2',..])<span style="font-size:25px;background-color:red">👁</span>
## df.replace(old_value, new_value)
# stringtext col_headers cellvalues
## filter 101 
### <span style="background-color:cyan;color:magenta;font-weight:bold">df.filter(regex='regex')</span>
### <span style="background-color:cyan;color:magenta;font-weight:bold">df.ix[row_index, column_name]</span>
### df.sample(n)
### shell + condition 
#### shell[cond] -return dataframe that meets condtion  
##### single direct
###### df[df['coln']=='x']
##### single negate
###### df[~df['coln']=='x']
##### multiple condtions
###### df[(cond1) and (cond2)]
###### df[df['coln'].isin(['x','y','z'])]
###### df[(~df['coln0']=='x') and (df['coln1']=='y')]
###### df.query('Age not in ['x','y','z']')
###### df.drop(df[df['Age'].isin(ages_to_drop)].index,inplace=True)
#### df.loc[df['coln']=='x','target_coln'] --update values
##### df.loc[df['Gender']='Manager','Years of experience']='Required'
## filter and  info&ensp;&nbsp;
### -----num_check
#### <span style="background-color:cyan;color:magenta;font-weight:bold">df['coln'].str.count('x')</span>
##### Count the occurrences of a specific substring in each string of a Series
##### eg<div >sentences = pd.Series([&emsp;'Python is fun', <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;&emsp;'I love Python', <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;&emsp;'Python programming is powerful'&emsp;])<br>python_counts = sentences.str.count('Python')<br>print(python_counts)<br>output:1 2 2 </div>
#### df['coln'].str.len() vs len()
##### len(df.col|ind|c)
* len(&ensp;df['coln']&emsp;) |count how many rows 
* len(df.columns&nbsp;) |count how many columns 
* len( &ensp;df.index &ensp;) | count how many rows 
##### df['coln'].srt.len()
* <table border="1" class="dataframe"><thead><tr style="text-align: right;"></tr></thead><tbody><tr><td> 1&emsp;subquery &emsp;&emsp;&ensp;&rarr;8.0</td></tr><tr><td>2&emsp;NaN &emsp;&emsp;&emsp;&emsp;&rarr;NaN</td></tr></tbody></table>
* return the length of each row's value
* import .srt.len() only applies to df series instead of the whole dataframe
### ------value access
#### df['coln'].str[n1] |indexing|
#### df['coln'].str[n1:n2] |slicer|
### ------check values
#### df['coln'].str.startswith('x')
#### df['coln'].str.endswith('x')
#### df['coln'].str.conatins('x')
#### df['coln'].str.match('x') &emsp;
##### columns header names must be unique , otherwise pandas won't be able to return the target the column 
# columns index type format case.
## column headers|index| names order-change
### column headers <br>reorder rearranged
#### ------column header names assignment
##### df.columns=['','','',..]
##### df.columns=df.iloc[0]
##### df.rename(columns={'key1':'val1',..},inplace=True)
##### <span style="background-color:cyan;color:magenta;font-weight:bold">df1=df.set_axis(['a', 'c'], axis='columns')</span> 
##### df.add_prefix('x')
##### df.add_suffix('y')
#### ------column header names' order rearranged
##### df.columns=[&ensp;['y','z','x']&ensp;]
##### &emsp;&rarr; nested list directly<ul><li>&emsp;&rarr; single list: column headers' names assignment<br>&emsp;&rarr; nested list: reordering 
##### df.reindex(columns=['x', 'y', 'z']) |reindex using col_hns
##### df.iloc(:,[3,2,1,0]) |rearranged column headers' index
##### df.pop('coln')&emsp;&rarr;insert(n,coln) 1 col_h_n to the first place 
###### col_poped=df.pop('col_n')
###### df.insert(loc=0, column='x', value=col_poped)
###### SYNTAX-Paramter explained
###### &emsp;&rarr;loc =position integer
###### &emsp;&rarr;column='str' assign column header names 
###### &emsp;&rarr;value=what's being popped
### row indeces <br>reorder rearranged
#### df.reindex( [' B ',' C ',' A '] )&nbsp;&rarr;&emsp;single level index 
*  pd.Series([1, 2, 3], index=['A', 'B', 'C'])
#### <span style="background-color:cyan;color:magenta;font-weight:bold">df.reorder_levels['a','b']&rarr;&emsp;multip level index</span> 
* pd.MultiIndex.from_arrays(arr, names=('class', 'diet'))
## datatype transform<br>string_formatting
### pd.to_numeric(df)
### df['coln'].astype('int')
### pd.to_datetime(df['coln'])
### df['coln'].to_string()
### map string formatting
#### % percentage  &emsp;
##### df[[&nbsp;'coln'&nbsp;]]=df[&nbsp;'coln'&nbsp;].map('{:.2%}'.format) 
#### cm suffix &emsp;&emsp;&emsp;&nbsp;
##### df[[&nbsp;'coln'&nbsp;]]=df[&nbsp;'coln'&nbsp;].map('{:.2%}cm'.format)
#### $  prefix&emsp;&emsp;&emsp;&emsp;&nbsp;
###### df[[&nbsp;'coln'&nbsp;]]=df[&nbsp;'coln'&nbsp;].map('${:.2%}').format
#### 3 digit separator&nbsp;
###### df[[&nbsp;'coln'&nbsp;]]=df[&nbsp;'coln'&nbsp;].map('{:,}'.format)
### apply lambda str format
#### % pct
##### df['coln'].apply(lambda x: srt(round(x*100，2)) + '%')
#### suffix&nbsp;
##### df['coln'].apply(lambda x: srt(round(x*100，2)) + '%')
#### prefix&nbsp;
##### df['coln'].apply(lambda x: srt('prefix + x)
#### 3&ensp;&ensp;K ,
##### df['coln'].apply(lambda x: srt(round(x*100，2)) + '%')
## cases capitalize
###### df['coln'].str.upper()
###### df['coln'].str.lower()
###### df['coln'].str.capitalize()
# update= alter existing |creat new
### update existing&ensp;&nbsp;<br> values
###### df.loc[]
* df.iloc[n,n]='x'
* df.loc[['',''],['','']]=['','','']
* <span style="background-color:cyan;color:magenta;font-weight:bold">df1.loc[df1['nan'].isna() ,'nan']=1|list</span> 
* &emsp;why -df.loc['row','col']=single newvalue| a list of new values
* &emsp;&rarr;  -df.loc['row_cond','col']=newvalue| a list of new values
* &emsp;&rarr; -df.loc[df['']=='x','col']=newvalue| a list of new values
###### df.at[]
* <span style="background-color:cyan;color:magenta;font-weight:bold">df1.at[1,'nan1']=9999 | single identical datatype</span> 
* &emsp;loc vs at
* &emsp;&rarr; df.at['row','col']=single new value 
* &emsp;&rarr; df.loc[df['']=='x','col']=single new value or| a list of new values
###### <span style="background-color:cyan;color:magenta;font-weight:bold">df['coln'].str.cat(sep)</span>
* concatenate strings in a Series or Index with a specified separator. 
* It can handle missing values and allows flexible concatenation with
* other Series, DataFrames, or list-like objects.
* eg<div>s = pd.Series(['a', 'b', np.nan, 'd']) <br>t = pd.Series(['x', 'y', 'z'], index=[0, 2, 3])<br>result = s.str.cat(t, join='outer', na_rep='-')<br>output: ax , b- , -y , dz2</div>
#### <span style="background-color:cyan;color:magenta;font-weight:bold">df.update()</span>
* update one df with another one 
* only the column that shares the same column header =vlookup
* <span style="background-color:cyan;color:magenta;font-weight:bold">the two dataframes must have identical shape</span>
#### df['coln'].str.strip()  |customizable|    
#### df['coln'].replace('old_str' ,'new_str')
#### df['coln'].map(mapper)
* mapper= {'key1':'val1',&nbsp;'key2':'val2'}
#### map&nbsp;🔠&nbsp;elementwise vs <br>apply🆎 columnwise <br>applymap(depricated❌)
##### ------map
###### 1.map key value pairs substitution
###### 2 dataframe whole df function application
###### &emsp;eg df.map(lambda x: len(str(x)))
###### &emsp;eg -----calculating the str len
* table : all the cell values have been <br>calcultaed and the length is returned
* <table border="1" class="dataframe"><thead><tr style="text-align: right;"><th>agg</th><th>Hello</th><th>cond</th><th>col1</th><th>cond</th><th>order by</th><th>col</th></tr></thead><tbody><tr><td>16</td><td>11</td><td>4</td><td>1</td><td>4</td><td>10</td><td>1</td></tr><tr><td>6</td><td>8</td><td>3</td><td>1</td><td>3</td><td>1</td><td>1</td></tr><tr><td>16</td><td>3</td><td>3</td><td>1</td><td>3</td><td>1</td><td>1</td></tr><tr><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr></tbody></table>
##### ------apply
###### df['coln'].apply(lambda x: x+2) | apply(function)
###### df['coln'].apply(lambda x: x+2) | passing one element at a time in only one column
###### df['coln'].apply(def)
###### apply vs map summary 
* apply(identical function to col )
* &emsp;df['num'].apply(np.sqrt)
* &emsp;works on entire Series objects rather than individual elements. <br>&emsp;column wise function -insead of elementwise on the whole dataframe(map)
### create new value
#### <span style="background-color:cyan;color:magenta;font-weight:bold">np.where[df['coln']=='x',True,False]&nbsp;</span> 
* boolean column  df['coln1']=np.where() 
* &emsp;purpose
* &emsp;&rarr; analysis -count 
* &emsp;&rarr; arguments acceptable 1:int 2:str :boolean 
#### <span style="background-color:cyan;color:magenta;font-weight:bold">df['coln'].mask(df['coln']=='x'&emsp;,o&emsp;)</span>
* &emsp;purpose
* &emsp;&rarr; analysis -count 
* &emsp;&rarr; arguments acceptable 1:int 2:str :boolean
#### <span style="background-color:cyan;color:magenta;font-weight:bold">np.where(df['c']=='x',1,0) vs .mask()</span>
* np.where() 2 returned values 
* df['col'].mask() 1 returnd value
* df['col'].mask() whatever doesnt meet the condition will remained intact </span>
#### entire new column | entire new row &emsp;
* df['new_coln']=['','',..]
* df.loc[n]=['','',..]&ensp;&emsp;&emsp;
* df.loc['x']=['','',..]&emsp;&emsp;
* df.loc vs df.iloc&emsp;&emsp;&ensp;
* &ensp;iloc is exlusively used forexisting data access and update
* &ensp;loc is reserved for creation of new rows 
# numeric symbols date arithmetic
## order rank &ensp;<br>sort
### df['coln'].rank()
#### syntax 
##### parameters
###### axis: 
* 0 or ‘index’ for rows and 
* 1 or ‘columns’ for Column.
###### method: Takes a string input<br>which tells pandas what to do with same values. 
* ‘average’, |default|
*  ‘min’,   
*  ‘max’, 
*  ‘first’,
*  ‘dense’) 
###### numeric_only:
* True - rank numeric values only 
* False- rank non-numeric values 
###### na_option: Takes 3 string input(
* ‘keep’, 
* 'top’, 
* ‘bottom’
###### ascending: 
* True -ascending
* False-descending
###### output table with all possible combination of parameters for reference : differences highlighted for easy comaprison 
* table
* ![rank](./images/rank.png "System Diagram" )
### df.sort_index()
### df.sort_values()
## comparison <br>operators
### df['coln'] >=n
### df['coln'] <= n
### df['coln'] != n
### df['coln'] == n |"*"
## range(start<br>&emsp; &emsp;&emsp;end)
### df['coln'].between(n1,n2)
### df['coln'].between(start,end)
## datetime&emsp;&nbsp;
### df['coln'] >'2026-05-06'
### notes📓
### <ol><li>1. after >|greater than before < |less </li><li>2. date must be passed in string format</li></ol>
## query&emsp;&emsp;&ensp;
##### df.query("catg='x' and val=2")
# <div style="background-color:red;color:white">Reshape<br>Join</div>
## check shape | overview of data
### df.info()
### df.shape
### df.describe()
### df.head()
### df.tail()
## <mark>Reshape</mark>
### pivot vs pivot_table
#### stick to pivot_table as it offers more flexiblity
##### syntax 
##### example1
##### example2
###### pivotable
###### <div style="border:dotted white;background-color:magenta">![datetime template](./images/pivot.png "System Diagram" )</div>
##### 
### stack vs unstack
#### ~ 
##### syntax 
##### example1
##### example2
###### stack
###### <div style="border:dotted white;background-color:teal">![datetime template](./images/stack.png "System Diagram" )</div>
##### 
### melt 
### cross tab
### groupby 
### explode 
## drop column | index row
### df.drop(columns=['x,'y',..])
### df.drop(index=[])
## Join
### Join   (index_based) can be igonored
### Merge  (flexible join+) best choice&emsp;&emsp;&nbsp;
#### syntax parameters
##### how=''
###### how="left",'right' similar to vlookup 
###### how='inner' intersection 
###### how='outer' all
##### on=' '&nbsp;
###### on='coln' only applies when two dataframes<br> that share the identical column header name
###### lefton='coln_df1' righton='coln_df2' <br>two dataframes have different column header names
### pd.concat (df1,df2,...) stacking ver|hor
#### syntax
#### &emsp;&rarr;pd.concat(df1,df2,..,axis=0)
#### &emsp;&rarr;axis=1 columns -vertical join fatter
#### &emsp;&rarr;axis=0 rows    -horizontal join thinner
#### vertical then column number and column header names and
#### their orders must be identical
#### horizontal then the indeces must be identical or the concate
#### won't be of any referential value 
# datetime
## creation &emsp;&nbsp;
### pd.date_range() |dynamic output.
#### pd.date_range(startdate, enddate, freq="n D|W|M|M|Y")
### pd.to_datetime()|single output ob 
#### format summary date(separator:empty space dash - backslash)
#### date(format YMD DMY YDM YMonD MonDY YDMon) 
#### time h:m:s 
#### template photo 
##### format template 
##### ![datetime template](./images/datetimeformat.png "System Diagram" )
### timezone difference handling 
#### Timezone Handling: Use the utc parameter in pd.to_datetime() to handle timezones.
### pd.to_datetime('20201111').date()
### pddate=pd.to_datetime('20201111').date()
### reading excel
#### pd.read_csv('',parse_dates=['datetime']  ,   index_col='datatime')
## strftime -string formatting time
####  df['coln'].dt.strftime('%d/%m/%Y')  
###### 📕 dt accessor must be used to form a chained method
###### syntax explained
## datetime object access 
### simple direct access 
#### pddate.month
#### pddate.year
#### pddate.day
## consolidate using groupby
### to_periods()
#### syntax | downside
##### argument 
###### 'D' (Daily), 
###### 'M' (Monthly), or 
###### 'Q' (Quarterly).
##### downside
###### when
######  plotting , the input should be the entire datetime object .<br>therefore the transformed date object<br> using to_period is not suitable for plotting. 
##### solution 
###### convert the date object back into timestamps 
* .dt.to_timestamp()
###### create new columns 
###### or using accessor to extract attributes of the datetime object<br> such as month day year 
* date.year
* date.quarter
* date.month
* <mark>date.dt.week</mark> week number 
* date.day
* date.hour
* date.minute
* date.dayofweek
### conversion|calculation access 
#### name
##### dayname
###### syntax
* df['coln'].dt.day_name()
###### example 
* df.groupby(df["date"]<mark>.dt.day_name()</mark>)["sales"].mean()
##### monthname
###### df['coln'].dt.month_name()
##### chinese locale='chinese'
#### number
##### daynumber 
###### df['coln'].day_of_week
##### weeknumber
###### df['coln'].dt.isocalendar().week
##### monthnumber 
###### df['coln'].month
##### quarternumber
###### df['coln'].quater
### df.set_index())resample
#### df.set_index('date').resample('M').mean()
### groupby(grouper())&emsp;&emsp;
#### df.groupby(pd.Grouper(key='date', freq='M')).mean() 
### groupby(dt.to_period())
#### df.groupby(df['date'].dt.to_period("M")).mean() 
## delta_gap | offset
### pd.Timestamp() object subtraction
#### how many days|
#### (date1-date2).day
#### <div style="background-color:cyan;color:indigo;border:double red;padding:5px"><span style="font-size:100px">🕰</span>timedelaVariable.total_seconds()<br> once you have calculated the total <br>seconds.then other units can be <br>deduced using division<div>
##### how many years |division
##### how many month |division
##### how many weeks |division 
##### how many days  |division
##### how many hours  |division
##### how many minutes |division
##### how mnay seconds  |division
### pd.Timedelta
#### syntax
##### pd.Timedelta(unit=n)
###### explained weeks=3
###### <div style="background-color:cyan;color:indigo;border:double red;padding:5px">weeks, days, hours, minutes, seconds, &emsp;milliseconds, microseconds, nanoseconds <br>&emsp;&rarr;❓why its called <mark>Timedelta</mark> - because month and year date object constitutent parts are not allowed</div>
### pd.offsets
#### month 
##### date1 + pd.offsets.MonthBegin(1)
##### date1 + pd.offsets.MonthEnd(1)
#### unit=n
##### date + pd.DateOffset(years=1)
##### date + pd.DateOffset(months=1)
##### date + pd.DateOffset(weeks=1)
##### date + pd.DateOffset(days=1)
##### date + pd.DateOffset(hours=1)
##### date + pd.DateOffset(minutes=1)
##### date + pd.DateOffset(seconds=1)
##### date + pd.DateOffset(milliseconds=1)
##### date + pd.DateOffset(microseconds=1)
##### date + pd.DateOffset(nanoseconds=1)
#### <mark>week</mark>&ensp;
##### syntax
##### date + pd.offsets.Week(weekday=0)
##### explained 
###### <span style="font-size:100px"> ![datetime template](./images/calendar.png "System Diagram" )</span> 
###### <div style="background-color:red;color:black;border:double red;padding:5px">0 represents monday which <br>means it starts from<br> monday and monday is <br>considered the first day of the week.</div>
## datetime filter
### prerequisite: datetime column as index 
#### syntax - 
##### df.loc['datetime1':'datetime2']
##### df.loc['2026-06-07 10:00:00']
## timezone
### creation of datetime without timezone
##### pd.date_range("2024-01-01 10:00", periods=3, freq="h")
### setting timezone 
##### date.tz_localize("UTC")
######  <span style="font-size:100px;background-color:green"> ![datetime template](./images/UTC.png "System Diagram" )</span> 
###### <div style="background-color:gold;color:black;border:double red;padding:5px">London, England<br>UTC is also known as Greenwich Mean Time (GMT),<br> as it is based on the time at the Prime Meridian,<br> which passes through the Royal Observatory<br> in Greenwich, London, England.</div>
### convsersion of timezone 
#### tz_convert('')
##### argument string format 
##### continent first backslash metropolitan city second 
###### dates_utc.tz_convert("Asia/Shanghai")
##### tz_ &rarr; timezone
## <mark>rolling-window</mark>
### df["sales"].rolling(window=7).mean()
### df['numerical_value coln'].rolling(window=n).agg()
## <span style="font-size:30px">📆</span><span style="background-color:cyan;color:magenta;font-weight:bold">calendar module</span>
### print calender
#### whole year&emsp; 
##### print(calendar.calendar(year,w=1,l=1))
#### single month 
###### default start day_of_week:Mon
* Default first day of the week is Monday
* print(calendar.month(year,month,w=n,l=n))
###### customized start day_of_week.
* calendar.TextCalendar(calendar.SUNDAY).prmonth(2020,12) 
* <div style="background-color:cyan;color:indigo">The function calendar.<mark>prmonth</mark> <br>(theyear,themonth,w=0,l=0) is part of Python's built-in calendar module. <br>Its purpose is straightforward it <mark>prints a formatted calendar for a specified month</mark>.</div>
### calculation &emsp;<br> verification 
#### leapDayYear 
##### is a given year a leapyear Boolean F T
###### calendar.isleap(year) 
##### how many leap days between two year
###### calendar.leapdays(year1,year2)
#### calculation...
##### calculate a date's day name of the week 
###### syntax calendar.weekday(year,month,day)
##### calculate the month's number of days and start day of the week 
###### calendar.monthrange(2026,10)
###### can be double checked using single month calendar 