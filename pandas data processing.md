
#   <div style="background-color:cyan;color:blue">![rank](./images/pddf1.png "s" )Pandas DataFrame&emsp;</div>
### load dataset
#### seaborn 
##### syntax 
###### iris_df = sns.load_dataset('iris')
###### titanic_df = sns.load_dataset('titanic')
###### tips_df = sns.load_dataset('tips')
##### available datasets
###### iris 
###### titanic
###### tips
###   <div style="background-color:blue;color:blue">![rank](./images/Enter_41039.png "s" )</div>read_files.
####  ![rank](./images/ext_csv_filetype_icon_176252.png "s" )pd.read_csv
##### csv  
###### abbrevaition 
* &emsp;c&rarr;comma &emsp;s &rarr; separated &emsp;&emsp;v- &rarr;value
###### sep=','
* 1 ','    &emsp;comma separated file
* 2 '\t'   &emsp;tab separated file
* 3 ';'   &emsp;semicolon separated file
* 4 ' '   &emsp;space separated file
* 5 '|'   &emsp;vertical bar separated file
##### syntax ![rank](./images/ext_csv_filetype_icon_176252.png "s" )
######  parameters selection
*    sep – specify delimiter (default is ,)
*    header – row number(s) to use as column names
*    index_col – set column(s) as index
*    usecols – load only specific columns
*    nrows – read only a fixed number of rows
*    skiprows – skip specific rows at start or by index*
######  parameters conversion
*    dtype – set data types for columns
*    parse_dates – parse date columns automatically
####  ![rank](./images/Excel_2013_23480.png "s" )pd.read_excel
##### xlsx  
###### xl&rarr;excel 
###### &emsp;s &rarr; spreadsheet
###### &emsp;&emsp;x- &rarr;cell
##### syntax ![rank](./images/Excel_2013_23480.png "s" )
######  parameters selection
* engine:='xlwings'.
* io: The path or URL of the Excel file.  <br>|same directory only file name and extension are required to be passed in as|
######  parameters selection
* sheet_name: The sheet to read. Default is 0 (first sheet).<br> Can be a string, integer, list, or None.
* header: Row number(s) to use as the column names. Default is 0.
* names: List of column names to use.
* index_col: Column(s) to set as index.
* usecols: Columns to parse.
* skiprows: Rows to skip at the start.
* nrows: Number of rows to parse.
######  parameters date dtype
* parse_dates: Parse dates.
* date_parser/date_format: Function or format for parsing dates.
* dtype: Data type for data or columns.
* converters: Dict of functions for converting values in certain columns.
* true_values/false_values: Values to consider as True/False.
######  parameters na handle
* na_values: Additional strings to recognize as NA/NaN.
* keep_default_na: Whether to include default NaN values when parsing data.
* na_filter: Detect missing value markers (empty strings and the value of na_values).
* verbose: Indicate number of NA values placed in non-numeric columns
######  parameters formatting  
* thousands/decimal: Thousands separator and decimal point character for parsing string columns to numeric.
* comment: Comments out remainder of line.skipfooter: Rows at the end to skip.
####  ![rank](./images/html_filetype_icon_177535.png "s" )pd.read_html
##### html  
###### ht&rarr;hypertext 
###### &emsp;ml &rarr; markup language
##### syntax ![rank](./images/html_filetype_icon_177535.png "s" )
######  parameters selection
*    io: A string, path object, or file-like object representing a URL or the HTML itself.
*    match: A regex or string to match text in the tables.
*    flavor: The parsing engine to use ('lxml', 'html5lib', 'bs4').
*    header: Row(s) to use as the column names.
*    index_col: Column(s) to set as index.
*    skiprows: Rows to skip after parsing the column integer.
*    parse_dates: Parse columns as dates.
###### parameter formatting
*    attrs: Dictionary of attributes to identify the table in the HTML.
*    thousands: Separator for thousands.
*    encoding: Encoding to decode the web page.
*    decimal: Character to recognize as decimal point.
###   <div style="background-color:white;color:blue">![rank](./images/notepad_pencil_checklist_clipboard_write_icon_142360.png "s" )</div>create df series.to_frame() 
##### list&emsp;&emsp;|s_df
###### pd.Series([,,,..]).to_frame()
##### tuple&emsp;|s_df
###### pd.Series((,,,..)).to_frame()
##### dict.&nbsp;&emsp;|s_df
###### pd.Series({'key1':'val1',&emsp;'key2':'val2'}).to_frame()
* only columns needed as index has already been given by keys
##### np.arry|s_df
###### pd.Series(np.array([,,,..])).to_frame()
###    <div style="background-color:white;color:blue">![rank](./images/notepad_pencil_checklist_clipboard_write_icon_142360.png "s" )</div>create df pd.DataFrame()&ensp; 
##### lists&emsp;&emsp;|df
###### pd.DataFrame([,,,..],[,,,..] ,index=['','',..],columns=['','',..])
* single lists 
* index and columns both are needed
##### tuples&ensp;&nbsp; |df
###### pd.DataFrame(((),(),..))
##### matrix&ensp;|df
###### pd.DataFrame(np.eye)
###### pd.DataFrame(np.identity)
###### pd.DataFrame(np.array([&nbsp;['','',''],['','',''],['','','']&nbsp;]))
##### dicts&nbsp;&emsp;&ensp;|df
###### pd.DataFrame(dict({"colh":['','',..],&ensp;"colh":['','',..] }), index=['',''..]
* columns headers have already been provided 
* using dictionary key - value is the content in the column
##### np.arrys|df
###### pd.DataFrame(np.array([['',''],['','']..]), index =['',''..] , columns =['','',..])
* nested lists
* columns headers and index are both needed
### frame 2 indeces
#### 1 row label     index row identifiers
##### assignment during creation using index=np.arange() or ['','']
#### 2 column label  columns column headers
##### assignment during creation using columns=np.arange() or ['',''] 
##### acess | update 
###### df.index=['','']
###### columns using integer is rare 
##### acess | update 
###### df.columns=['','']
###   ![rank](./images/check_out_icon_176385.png "s" )df.to_file&emsp;
#### ![rank](./images/ext_csv_filetype_icon_176252.png "s" )df.to_csv('filename.csv')
####  ![rank](./images/Excel_2013_23480.png "s" )df.to_excel('filename.xlsx')
#### ![rank](./images/html_filetype_icon_177535.png "s" )df.to_html('filename.html')
##### html table :1 excel to or 2 df 
##### convert df to html 
##### convert excel to html
###### step 1 : 1.1 read_excel 1.2 create datainput
###### step 2 : convert datainput read_in as df
###### step 3 : html_table_1 = df1.to_html(index=False, border=1)\
###### step 4 : with open("table.html", "w", encoding="utf-8") as f:<br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;f.write(html_table_1)
#  <div style="background-color:green;color:indigo">![rank](./images/tablegeneral.png "s" )agg summary window
##     <div style="background-color:yellow;color:indigo;font-weight:bold">![rank](./images/statistics.png "s" ) </div>statistical overview 
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
### df.unique()
#### len(df.unique()) how many number of unqiue values in a column
##### use case 
###### 1 crosstab
* the total number of rows when using crosstab to reconstruct 
* dataframe using multiple columns as argument for index parameter 
* len(df['coln1'].unique())  * len(df['coln2'].unique()) 
###### 2 catagory
* how many catagory does a column contains
* how many unique product codes are there in a column 
* how many emeployees are there in a company 
### df.describe().
### df['coln'].describe
### df.mean()
### df.median()
### df.mode()
### df.count()
##   <div style="background-color:magenta;color:white;font-weight:bold">![rank](./images/book-information-button_icon-icons.com_71738.png "s" )</div>df.info()  | na entry&nbsp;
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
##  <div style="background-color:maroon;color:silver;font-weight:bold">![rank](./images/barchart_icon-icons.com_71903.png "s" )</div>df.value_count()&emsp;
### useful for counting repeated values such as age
###  how many people are at the age of 20
### catagorical data -count - each catagory 's count
### quick insight 
#### how many business unites are there in a compnay 
#### how many product families are there in each business unite
#### how many combination serieses of each single family 
#### how many combination components of the each sseries 
##  <div style="background-color:teal;color:black;font-weight:bold">![rank](./images/category_icon_183800.png "s" )</div>df['age'].count() &ensp;&ensp;
### simple calculation of the total instances
### value_counts vs count 
##### value_counts() counts catagorical value's number of  occurances
##### count is the total number of occurances regardless of its category  
### simplest count
##### a column's total number of values 
##### how many entries of records within a column 
## <div style="background-color:cyan;color:magenta;font-weight:bold">  ![rank](./images/grid_pixel_icon_123662.png "s" )</div>df.transformVSagg<br>&emsp;&emsp;&emsp;&emsp;&nbsp;VS apply
### comparison table
#### apply flexible 
##### it can apply a function 
###### along an axis 
######  or a grouped dataframe .it can handle both 
* row_wise 
* column_wise  operation 
###### output 
* scalar 
* series 
* dataframe
#### dataframe size&emsp; &rarr;&emsp;<br>&emsp;transform = &emsp; &emsp;&emsp; &emsp;<br>&emsp;agg &emsp;&emsp;&nbsp;&nbsp;<
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
## <div style="background-color:cyan;color:magenta;font-weight:bold">  ![rank](./images/windows-square-shape-brand_icon-icons.com_59109.png "s" )</div>df['col'].transform() 
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
#  <div style="background-color:teal;color:maroon">![rank](./images/dashboard.png "s" )plt for self reference&ensp;&nbsp;
## single plot types overview
### <mark>relplot |  lmplot </mark> marker | linesgement <br>&emsp;continuous data | treand over time.<br>&ensp;&rarr;a marker is the data point which is composed of x y coordinates<br>&ensp;&rarr;lm represents linear model that deals with regression <br>&emsp; 
####   <div style="background-color:cyan;color:indigo;border:double green">![rank](./images/Line-chart256_25044.png "s" )![rank](./images/analytics_finance_business_visualization_graph_scatter_icon_266053.png "s" )![rank](./images/regression-analysis.png "s" )![rank](./images/regression.png "s" )</div> line scatter &emsp;regression<br>
### <mark>catplot</mark> catagorical data |purpose <br>&emsp;performance contribution compare.<br>&ensp;&rarr;a bar or slice of a pie represents a catagory's height|contribution
####   <div style="background-color:cyan;color:indigo">![rank](./images/Bar-chart_37150.png "s" )![rank](./images/bar_chart_horizontal_sorted_icon_183418.png "s" )![rank](./images/pie_chart_icon_205092.png "s" )![rank](./images/area_chart_icon_183372.png "s" )</div> bar barh pie &nbsp;area 
###  <mark>displot</mark>  frequency | bins bar or curve <br>&emsp;distribution central tendency outlier<br>&ensp;&rarr;box the majority - whicker outliers |fill  bins at fixed interval curve
####   <div style="background-color:cyan;color:indigo">![rank](./images/visualize_visualization_analytics_finance_business_box_plot_icon_266087.png "s" )![rank](./images/histogram_chart_icon_215771.png "s" )![rank](./images/histogram_icon_155274.png "s" )</div>box &nbsp;hist &nbsp;kde
##### kde | his 
*  hist &rarr;&nbsp; bars 1width with represent bins boundaries 
*  &emsp; &emsp; &emsp; &emsp; &ensp;2height repsents frequency 
*  kde &rarr;kernel density estimation 
*  &emsp; smooth out the edges of the bins|bars to form a curve 
*  &emsp; &rarr;smoothed continuous version of histogram
##### box | whisker
* box the 50% four quartiles 
* spot outliers 
## ax vs figure
### figure canvas 
### ax each individual plot 
### axes , fig=plt.subplots(n1,n2,figsize(n3,n4))
## mul plot types |correlation
### pairplot
#### sns.pairplot(data)
##### parameter 
###### data specifier
*    vars=None,
*    x_vars=None,
*    y_vars=None,
*    dropna=False,
###### sub-group
*    hue=None,
*    hue_order=None,
###### diagonal plot type  
*    diag_kws=None,    |diag_kws={'multiple':'stack'})
*    &emsp;kws &rarr;key words &rarr; a dictionary is expected
*    diag_kind='auto', |kde
###### plot type
*    kind='scatter',
###### styling  
*    palette=None,
*    markers=None,
*    height=2.5,
*    aspect=1,
*    corner=False,
*    plot_kws=None,
*    grid_kws=None,
*    size=None,
##### parameters blocks
###### block
###### <div style="background-color:yellow;color:magenta;border:double cyan">sns.pairplot(data,*,hue=None,hue_order=None,palette=None,<br>&emsp;vars=None,x_vars=None,y_vars=None,kind='scatter',<br>&emsp;diag_kind='auto',markers=None,height=2.5,aspect=1,<br>&emsp;corner=False,dropna=False,plot_kws=None,diag_kws=None,<br>&emsp;grid_kws=None,size=None,)</div>
##### illustration
#####  <div style="background-color:indigo">![rank](./images/pairplot_3_0.png "s" )</div>
### jointplot =<br>&emsp;scatter + dist
#### 
##### illustration
#####  <div style="background-color:indigo">![rank](./images/jointplot.png "s" )</div>
### heatmap
#### sns.heatmap(df.corr())
##### illustration
#####  <div style="background-color:indigo">![rank](./images/structured_heatmap.png "s" )</div>
###### principle 
###### display data in matrix which is color coded to 
* show the relationship bwteen fetures 
* recognize cluster with data 
###### <mark>best practice </amrk>
* &emsp;if not crowded - annotation
* &emsp;if its too crowded add vertical Color bar or legend for reference of the value range 
## mutiple plot grid plot <br>subplot 
### syntax 
#### &emsp;axes, fig =plt.subplot(row_number |2|,col_number |2|,figsize=(width, height))
#### parameters |spacing
#####  automatic| fig.tight_layout()
* automatically adjust subplot paramters to give specified padding
* &emsp;pad  |subplot with the overall figure edge
* &emsp;h_pad w_pad =floats |subplot with adjacent one|
##### mannual | plt.subplots_adjust()
###### adjust spacing between suplots 
###### parameters
* left: The position of the left edge of the subplots, as a fraction of the figure width.
* right: The position of the right edge of the subplots, as a fraction of the figure width
* bottom: The position of the bottom edge of the subplots, as a fraction of the figure height.
* top: The position of the top edge of the subplots, as a fraction of the figure height.
* wspace: The width of the padding between subplots, as a fraction of the average Axes width.
* 
hspace: The height of the padding between subplots, as a fraction of the average Axes height.
#### parameter size
##### overall figsize(contains all subplots)
* Note:
* &emsp;figsize affects the whole figure; subplot sizes scale accordingly.
* ajustment after plotting
* &emsp;fig.set_size_inches(12, 6)
* setting during plotting
* &emsp;plt.subplots(n0,n1,figsize(n2,n3))
* &emsp;&emsp;figsize=(width,height) is in inch and applies to the entire figure
##### indiviual size for each subplot 
* principle: through ratio adjusting, one may get larger or smller ratio
* gridspec_kw={:} 
* &emsp; &emsp;{'width_ratios'：[n1,n2]}
* &emsp;&emsp;{'height_ratios'：[n1,n2]} 
*&emsp; fig, ax = plt.subplots(1, 2, figsize=(8, 4), gridspec_kw={'width_ratios': [3, 1]})
### <div style="background-color:magenta;border:dotted white">&emsp;ax[0,0].plot&emsp; <br>&emsp;ax[0,1].plot&emsp; <br>&emsp;ax[1,0].plot&emsp;<br>&emsp;ax[1,1].plot&emsp;</div>
### purpose
#### 1 comparing different datasets
#### 2 comparing different visuals of the same dataset
## plot summary -all libraries <br> to be updated
###   <div style="background-color:indigo">![rank](./images/pandas_logo_icon_248897.png "s" )</div>pandas | simpliest<br>df['col'].plot(kind='')
#### syntax - df['coln'].plot(kind='')
#### df['coln'].plot()
##### syntax parameters
###### example : df.plot(kind='scatter', x='Height', y='Weight', title='Height vs Weight', <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;xlabel='Height (cm)', ylabel='Weight (kg)', figsize=(8, 5))
###### kind=""
* line 
* bar  | barh
* hist | kde
* scatter
* box
* pie
* area
###### data parameters
* x	-data array|column_name x='colname' 
* y -data array|column_name y='colname'
###### annotation parameters
* title	='sales over time'
* xlabel='x'
* ylabel='y'
* plt.legend 
* &emsp;plt.legend(['A Label', 'B Label', 'C Label', 'D Label'], loc='center left', bbox_to_anchor=(1, 0.5))
###### formatting parameters
* color='blue'
* figsiz=(&emsp;8&emsp;,&emsp;2&emsp;)
* autopct='%1.1f%%'
##### plt.legend 
###### plt.legend(['A Label', 'B Label', 'C Label', 'D Label'], loc='center left', bbox_to_anchor=(1, 0.5))
##### other styling related used matplotlib 
####   ![rank](./images/chart_histogram_icon_138776.png "s" )df.hist()
##### quick check of distributon 
##### bins 
##### parameters 
####  combination &ensp;
##### pandas plot for quick analysis for self reference only 
##### plt and seaborn -seaborn main focus plt adding details and formatting 
##### quickest and simpliest for self reference
### <div style="background-color:cyan">![rank](./images/matplotlib.png "s" )</div>matplotlib
#### can be used in combinations with other libarary to add more details 
#### syntax 
##### line
###### df['coln'].plot() 
* no x and y paramters are required , only need to pass in x and y data in proper order
### <div style="background-color:green">![rank](./images/seaborn-icon.png "s" )</div>seaborn
#### characteristics 
##### built directly on top of matplotlib
##### appealing for statistical plotting 
##### multi level split data into groups
###### hue 
###### coln rown  
* forms a grid of n columns and n rows 
##### professional rendering effect 
#### syntax 
##### df['coln'].plot(kind='')
### <div style="background-color:gold">![rank](./images/sympy.png "s" )</div>sympy math 
#### equation
#### syntax 
##### symbols must be set up for variables 
##### sympy.plot()
### <div style="background-color:black">![rank](./images/manim.png "s" )</div>manim
#### equation  for animation 
#### 
##### df['coln'].plot(kind='')
### <div style="background-color:lightblue">![rank](./images/plotly_logo_icon_248823.png "s" )</div>dash plotly 
#### syntax -to be updated 
##### df['coln'].plot(kind='')
##### funnel chart business
##### sunburst
##### timeline 
###### track progress
##### 
#  <div style="background-color:silver;color:crimson">![rank](./images/update.png "s" )update -existing new &nbsp;</div>
## nan missing values + duplicates.
## 👁️‍🗨️df['coln'].notna()&ensp;&nbsp;
#### identify 
### 👁️‍🗨️df['coln'].isna()&emsp;&nbsp;
#### identify 
##### alternative methods for identifying nan
###### pandas
* 1 sort_values(na_position)
* 2 df.info
* 3 df.isna() <br> &emsp; df.isna().sort_values(by="coln",ascending=True)
###### numpy
* only works for numpy array
* np.isnan(np.array([1,23,np.nan]))
###### 
### ✍df['coln'].fillna()&emsp;
#### handle -replace it with a more sensible value 
#### replace
##### =df['coln'].replace(np.nan,None)
* timeseries 
* df.ffill() df.bfill()
* fillna(mean)
* df['Cat'] = df['Cat'].fillna(df['Cate'].mode()[0])
* fillna(dict)
* df.fillna(value={'A': 0, 'B': 1,'C': 'Missing'}) 
### ⛔df['coln'].dropna()
* handle -drop
### <span style="background-color:cyan;color:magenta;font-weight:bold">💈df.interpolate()n</span>
#### interpolate na 
#####  fill missing values (NaN) in a DataFrame or Series using various interpolation techniques. 
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
## stringtext <br>col_headers cellvalues<br>  index column label
### filter 101 
#### <span style="background-color:cyan;color:magenta;font-weight:bold">df.filter(regex='regex')</span>
##### <span style="background-color:cyan;color:magenta;font-weight:bold">df.ix[row_index, column_name]</span>
#### df.sample(n)
#### shell + condition 
##### shell[cond] -return dataframe that meets condtion  
###### single direct
* df[df['coln']=='x']
###### single negate
* df[~df['coln']=='x']
###### multiple condtions
* df[(cond1) and (cond2)]
* df[df['coln'].isin(['x','y','z'])]
* df[(~df['coln0']=='x') and (df['coln1']=='y')]
* df.query('Age not in ['x','y','z']')
* df.drop(df[df['Age'].isin(ages_to_drop)].index,inplace=True)
##### df.loc[df['coln']=='x','target_coln'] --update values
###### df.loc[df['Gender']='Manager','Years of experience']='Required'
### filter and  info&ensp;&nbsp;
#### -----num_check
##### <span style="background-color:cyan;color:magenta;font-weight:bold">df['coln'].str.count('x')</span>
###### Count the occurrences of a specific substring in each string of a Series
###### eg<div >sentences = pd.Series([&emsp;'Python is fun', <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;&emsp;'I love Python', <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;&emsp;'Python programming is powerful'&emsp;])<br>python_counts = sentences.str.count('Python')<br>print(python_counts)<br>output:1 2 2 </div>
##### df['coln'].str.len() vs len()
###### len(df.col|ind|c)
* len(&ensp;df['coln']&emsp;) |count how many rows 
* len(df.columns&nbsp;) |count how many columns 
* len( &ensp;df.index &ensp;) | count how many rows 
###### df['coln'].srt.len()
* <table border="1" class="dataframe"><thead><tr style="text-align: right;"></tr></thead><tbody><tr><td> 1&emsp;subquery &emsp;&emsp;&ensp;&rarr;8.0</td></tr><tr><td>2&emsp;NaN &emsp;&emsp;&emsp;&emsp;&rarr;NaN</td></tr></tbody></table>
* return the length of each row's value
* import .srt.len() only applies to df series instead of the whole dataframe
#### ------value access
##### df['coln'].str[n1] |indexing|
##### df['coln'].str[n1:n2] |slicer|
#### ------check values
##### df['coln'].str.startswith('x')
##### df['coln'].str.endswith('x')
##### df['coln'].str.conatins('x')
##### df['coln'].str.match('x') &emsp;
###### columns header names must be unique , otherwise pandas won't be able to return the target the column 
## index column label row label <br> format case.
### index column label row labels<br>column headers|index| names order-change
#### column headers <br>reorder rearranged
##### column header names assignment
###### <span style="background-color:magenta">df.columns=['x']</span>
* comment by default pandas's dataframe's columns attribute 
* expect a list of entries  therefore, 
* <mark>even if only one column header exists</mark>,
*  the substitution must also be wrapped in a pair of square brackets 
###### df.columns=['','','',..]
###### df.columns=df.iloc[0]
###### df.rename(columns={'key1':'val1',..},inplace=True)
###### <span style="background-color:cyan;color:magenta;font-weight:bold">df1=df.set_axis(['a', 'c'], axis='columns')</span> 
###### df.add_prefix('x')
###### df.add_suffix('y')
##### ------column header names' order rearranged
###### df.columns=[&ensp;['y','z','x']&ensp;]
###### &emsp;&rarr; nested list directly<ul><li>&emsp;&rarr; single list: column headers' names assignment<br>&emsp;&rarr; nested list: reordering 
###### df.reindex(columns=['x', 'y', 'z']) |reindex using col_hns
###### df.iloc(:,[3,2,1,0]) |rearranged column headers' index
###### df.pop('coln')&emsp;&rarr;insert(n,coln) 1 col_h_n to the first place 
* col_poped=df.pop('col_n')
* df.insert(loc=0, column='x', value=col_poped)
* SYNTAX-Paramter explained
* &emsp;&rarr;loc =position integer
* &emsp;&rarr;column='str' assign column header names 
* &emsp;&rarr;value=what's being popped
#### index row labels <br>reorder rearranged
##### df.reindex( [' B ',' C ',' A '] )&nbsp;&rarr;&emsp;single level index 
*  pd.Series([1, 2, 3], index=['A', 'B', 'C'])
##### <span style="background-color:cyan;color:magenta;font-weight:bold">df.reorder_levels['a','b']&rarr;&emsp;multip level index</span> 
* pd.MultiIndex.from_arrays(arr, names=('class', 'diet'))
### datatype change<br>string_formatting
#### pd.to_numeric(df)
#### df['coln'].astype('int')
#### pd.to_datetime(df['coln'])
#### df['coln'].to_string()
#### map string formatting
##### syntax explnanation 
###### df['coln'].map(mapper)
###### mappper -breakdown 
* <span style='background-color:maroon'>'{}'.format</span> is equivalent to f'{}'
* &emsp;&rarr;why we use the former syntax 
* &emsp;&rarr;if we try to incorporate a lambda inside the <br>&emsp;&emsp;string formatting method , its more flexible 
* use case example 
* convert decimal floats into percentage 
* &emsp;breakdown 
* &emsp;'{}'.format()  within format method the x input can be further processed
###### example code bolck 
* code block
* <div style="background-color:white;color:maroon;border:double white">df[&nbsp;'coln'&nbsp;].map(&emsp;lambda x:&emsp; '{&emsp;<mark>&ensp;:&ensp;</mark>.2f&emsp;}%'.<u><b><span style='background-color:cyan;color:indigo'>format(x * 100)</b></u></span>)<br>&emsp;&emsp;&emsp;&emsp;&emsp;1 &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;3&emsp;&emsp;&nbsp;4&emsp;<span style="background-color:cyan">&emsp;&emsp;&emsp;2&emsp;&emsp;&emsp;</span> <br>&emsp;&rarr;first :  map method passes x input into lambda function <br>&emsp;&rarr;second format method carries out arithmetic operation by <br>&emsp;&emsp;multipling x by a factor of 100<br>&emsp;&rarr;third |.2f =2 floating points| keep two decimal places<br>&emsp;&rarr;fourth concatenation of <span style='background-color:green;color:white;border:dotted black'>x*100.2f </span>and  <span style='background-color:magenta;color:white;border:dotted black'>%</span> sign </div>
##### % percentage  &emsp;
###### df[[&nbsp;'coln'&nbsp;]]=df[&nbsp;'coln'&nbsp;].map(lambda x: '{:.2f}%'.format(x * 100))
##### cm suffix &emsp;&emsp;&emsp;&nbsp;
###### df[[&nbsp;'coln'&nbsp;]]=df[&nbsp;'coln'&nbsp;].map('{:.2}cm'.format)
##### $  prefix&emsp;&emsp;&emsp;&emsp;&nbsp;
* df[[&nbsp;'coln'&nbsp;]]=df[&nbsp;'coln'&nbsp;].map('${:.2}'.format)
##### 3 digit separator&nbsp;
* df[[&nbsp;'coln'&nbsp;]]=df[&nbsp;'coln'&nbsp;].map('{:,}'.format)
#### apply lambda str format
##### % percentage
###### df['coln'].apply(lambda x: srt(round(x*100，2)) + '%')
##### cm suffix&nbsp;
###### df['coln'].apply(lambda x: srt(x + 'cm')
##### $prefix&nbsp;
###### df['coln'].apply(lambda x: srt( '$' + x)
##### 3&ensp;&ensp;K ,
###### df['coln'].applyapply(lambda x: f"{x : ,.0f}
### apply vs map in str formatting 
#### apply(lambda x:str()) is more intuitive complex 
#### map('{:.2f}'.format) syntax is shorter simpler works on series 
### cases capitalize
* A 
* &emsp;df['coln'].str.upper()
* &emsp;df['coln'].str.capitalize()
* &emsp;df['coln'].str.title()
* a
* &emsp;df['coln'].str.lower()
* &emsp;df['coln'].str.casefold()
* ~A|a
* &emsp;df['coln'].str.swapcase()
## update= alter existing |creat new
#### update existing&ensp;&nbsp;<br> values
##### using filer
###### loc=
* df.loc[]
* -------
* df.iloc[n,n]='x'
* df.loc[['',''],['','']]=['','','']
* <span style="background-color:cyan;color:magenta;font-weight:bold">df1.loc[df1['nan'].isna() ,'nan']=1|list</span> 
* &emsp;why -df.loc['row','col']=single newvalue| a list of new values
* &emsp;&rarr;  -df.loc['row_cond','col']=newvalue| a list of new values
* &emsp;&rarr; -df.loc[df['']=='x','col']=newvalue| a list of new values
###### at
* <span style="background-color:cyan;color:magenta;font-weight:bold">df1.at[1,'nan1']=9999 | single identical datatype</span> 
* &emsp;loc vs at
* &emsp;&rarr; df.at['row','col']=single new value 
* &emsp;&rarr; df.loc[df['']=='x','col']=single new value or| a list of new values
##### <span style="background-color:cyan;color:magenta;font-weight:bold">df.update()</span>
* update one df with another one 
* only the column that shares the same column header =vlookup
* <span style="background-color:cyan;color:magenta;font-weight:bold">the two dataframes must have identical shape</span>
##### df['coln'].str.strip()  |customizable|    
##### df['coln'].replace('old_str' ,'new_str')
##### df['coln'].map(mapper)
* mapper= {'key1':'val1',&nbsp;'key2':'val2'}
##### map&nbsp;🔠&nbsp;elementwise vs <br>apply🆎 columnwise <br>applymap(depricated❌)
###### ------map
* 1.map key value pairs substitution
* 2 dataframe whole df function application
* &emsp;eg df.map(lambda x: len(str(x)))
* &emsp;eg -----calculating the str len
* table : all the cell values have been <br>calcultaed and the length is returned
* <table border="1" class="dataframe"><thead><tr style="text-align: right;"><th>agg</th><th>Hello</th><th>cond</th><th>col1</th><th>cond</th><th>order by</th><th>col</th></tr></thead><tbody><tr><td>16</td><td>11</td><td>4</td><td>1</td><td>4</td><td>10</td><td>1</td></tr><tr><td>6</td><td>8</td><td>3</td><td>1</td><td>3</td><td>1</td><td>1</td></tr><tr><td>16</td><td>3</td><td>3</td><td>1</td><td>3</td><td>1</td><td>1</td></tr><tr><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr></tbody></table>
###### ------apply
* df['coln'].apply(lambda x: x+2) | apply(function)
* df['coln'].apply(lambda x: x+2) | passing one element at a time in only one column
* df['coln'].apply(def)
*  apply vs map summary 
* apply(identical function to col )
* &emsp;df['num'].apply(np.sqrt)
* &emsp;works on entire Series objects rather than individual elements. <br>&emsp;column wise function -insead of elementwise on the whole dataframe(map)
#### str ？
##### isxxx&emsp;&emsp;
###### isalnum(): 
* Checks if all characters are alphanumeric.
###### isalpha(): 
* Checks if all characters are alphabetic.
###### isdigit(): 
* Checks if all characters are digits.
###### isspace(): 
* Checks if all characters are whitespace.
###### istitle():
* Checks if the string is in title case.
###### islower():
* Checks if all characters are lowercase.
###### isupper():
* Checks if all characters are uppercase.
##### Find substrings
###### find -1st ocurrance
* find(sub, start=0, end=len(str)): Returns the lowest index of the substring.
* example 
* &emsp;s = 'hello world hello'
* &emsp;s.find('hello')    # => 0
* &emsp;s.rfind('hello')   # => 12
* &emsp;s.find('xyz')      # => -1
###### index -1st ocurrance&emsp;&emsp;
* function 
* &emsp; use substring as argument to return its index 
* index(sub, start=0, end=len(str)): Same as find() but raises an error if not found.
* examples 
* &emsp; colors = ["red", "blue", "green", "blue"]print(colors.index("blue"))  # Output: 1
* <div style="background-color:indigo">&emsp;&emsp;&rarr;the returned integer is <br>&emsp;&emsp;;&emsp;the first occurance of the passed value|substring</div>
###### find vs index
* find() returns -1 on miss, 
* index() raises ValueError.
###### count how many occurances 
* syntax 
* &emsp; list|string.count('substring|value')
* function 
* &emsp;The count() method in Python is used to count the <mark>number of<br>&emsp; occurrences</mark> of a specified value in a list or string.
* exmaple 1 string
* &emsp; fruits = ['apple', 'banana', 'cherry', 'apple', 'cherry'] <br>&emsp;count_apple = fruits.count('apple')  Output: 2
* example 2 list
* &emsp; fruits = ['apple', 'banana', 'cherry', 'apple', 'cherry'] <br>&emsp;count_apple = fruits.count('apple') Output: 2
###### str.conatins
###### str.startswith
###### str.endswit
#### str [:]
###### str[start:stop:step]
###### negative index
* s_string_slice[:-2]    # => 'abcd'
###### negative step |reverse order
* 'hello'[::-1]   # => 'olleh'
#### <span style='background-color:magenta'>str~🔐</span>
##### center
###### center(width, fillchar=' '): Centers the string with optional fill characters.
##### encode|decode
###### example 
###### b = 'café'.encode('utf-8')  b.decode('utf-8')  
##### zfill&emsp;&nbsp;
##### f string formatting 
###### decimal places for floats
* pi = 3.14159 f"{pi:.2f}"          # => '3.14'
###### thousand comma separator
* f"{1000000:,}"       # => '1,000,000'
###### alignment by inserting empty spaces 
* f"{'hi':>10}"        # => '        hi'
* '{:>5}'.format('hi')
* white space calculation methods 
* &emsp; 1 '{:>5}'.format('hi') .count(' ') &rarr; 3 three empty space
* &emsp; 2 len('{:>5}'.format('hi'))-len('{:}'.format('hi')) &rarr; 3
* len('{:>5}'.format('hi'))&emsp;&emsp;          &rarr; 5 total length including empty space 
* len('{:}'.format('hi'))&emsp;&emsp;&emsp;         &rarr;  2 total length of the string value 
###### method for transformation|information 
* f string format
*  items = ['a', 'b', 'c'] <br> f"{len(items)} items: {', '.join(items)}"   # => '3 items: a, b, c'
* &emsp;&rarr;f"{len(items)} : {', '.join(items)}"   # => '3 : a, b, c'
*  &emsp;&rarr;f"{len(items)} "   # => '3'
*  &emsp;&rarr;f"{ : }"   # => ' : '
*  &emsp;&rarr;f"{', '.join(items)}"   # => ' a, b, c'
* arithmetic operation
* &emsp;&rarr; x = 42  f"{x * 2 = }"   # => 'x * 2 = 84'
###### placeholder for update 
* '{0} then {1}'.format('first', 'second')   # => 'first then second'
* '{} and {}'.format('A', 'B')               # => 'A and B'
* '{name} is {age}'.format(name='Alice', age=30)   # => 'Alice is 30'
##### zerofilling-padding
###### zfill(width): Pads the string with zeros on the left.
##### translate
###### to be continued
#### split
##### split vs partition 
###### split flexible limit by setting maxsplit =n 
###### partition rigid only 3 parts separated by one delimitrer
##### split
###### split paragraph into listed strings
* paragraph.split(sep=None, maxsplit=-1)  
* sep &rarr; separator 
* maxsplit default -1 which means no limit 
###### rsplit lsplit
##### splitlines
###### splitlines(keepends=False): Splits the string at line breaks.
###### function
*  By default, splitlines() removes the line break characters from the resulting list elements.
*   If no line breaks are found, it returns a list containing the original string as a <mark>single element</mark>.
###### example
* text = "Line1\nLine2\r\nLine3"
&emsp;&rarr;Output: ['Line1<mark>\n</mark>', 'Line2<mark>\r\n'</mark>, 'Line3']
* text = "One\n\nTwo\nThree"
&emsp;&rarr;Output: ['One', '', 'Two', 'Three']
###### argument
* True &rarr;keep the line breaks 
##### partition
###### <mark>&emsp;3&emsp;</mark>
###### partition() splits into exactly three parts:<mark>before, separator, after</mark>. <br>Useful when you need the delimiter too.
* example
* normal partition :separator must match 
* &emsp;'key=value'.partition('=')    # => ('key', '=', 'value')
* 'no-sep'.partition('=')      # => ('no-sep', '', '')
* partition from right
* &emsp; 'a.b.c'.rpartition('.')       # => ('a.b', '.', 'c')
* unpack partition results
* &emsp;header, _, body = 'Subject: Hello'.partition(': ')&rarr;lheader   # => 'Subject' |body     # => 'Hello'
#### str-
##### str.strip
###### str.strip(seperator)
###### example
* names = [" Alice ", "\tBob\n", " Charlie "] &rarr;cleaned = [n.strip() for n in names]
###### common pitfalls
* notes
* <div style="background-color:indigo">Does not remove characters from the middle of the string.<br> Passing "abc" removes all 'a', 'b', 'c' from both ends, not "abc" as a block.</div> Output: ['Alice', 'Bob', 'Charlie']
##### str.replace
###### str.replace(oldvalue,newvlaue)
#### str+
#####  <span style="background-color:cyan;color:magenta;font-weight:bold">str.cat()</span>
###### &emsp;<span style="background-color:cyan;color:indigo">&emsp;🔖note&emsp;</span> 
* concatenate <mark>strings</mark> in a Series or Index with a <mark>specified separator.</mark> 
* &emsp;It can handle missing values and allows flexible concatenation with
* &emsp;<span style="background-color:magenta">other Series, DataFrames, or list-like objects.</span>
###### example&emsp;&emsp; 
* &emsp;eg<div>&emsp;s = pd.Series(['a', 'b', np.nan, 'd']) <br>&emsp;t = pd.Series(['x', 'y', 'z'], index=[0, 2, 3])&emsp;<br>&emsp;result = s.str.cat(t, join='outer', na_rep='-')<br>&emsp;output: ax , b- , -y , dz2</div>
##### '-'.join()
###### function
* notes 
* <div style='background-color:brown;border:dotted '>The join() method in Python is used to <mark>concatenate the elements of an iterable </mark><br>&emsp;(like a list, tuple, or set) into a <span style="background-color:cyan;color:indigo">single string</span>, with a specified separator between each element.<ol><li>Iterables &rarr;</li><li>&emsp;def ：1. to utter again or repeatedly.<br>&emsp;&emsp;&emsp;&ensp;&nbsp;2. to do (something) over again or repeatedly. </li><li>&emsp;synonums:  reiterate, repeat, restate.</li></ol></div>
###### examples
* 1 list    "-".join(['a','b','c']) &rarr; a-b-c
* 2 tuple   "-".join(('a','b','c')) &rarr; a-b-c
* 3 set     "-".join({'a','b','c'}) &rarr; a-b-c
* 4 dict    "-".join({'a':1,'b':2,'c':3}) &rarr; a-b-c  
* 4 <span style="background-color:magenta">dict only applies to the keys </span>values won't affecte
* 5. dataframe (most useful case)  df_string1.apply(lambda x:':'.join(x),axis=0)
*   ![rank](./images/appjoinondataframe.png "s" )
##### + operator
###### df['joined']=df['firstname']+df['lastname']
###### productid + product name
##### + cat join comparison
###### + simple 
* cumbsersome if it involves separator , as a single colummn of separator needs to be created prior to the join
###### 👍 cat 
* flexible 
* two columns must all be strings 
* use str()  to convert by assigning a new column first
###### join
* limited 
* dataframe must all be strings 
* only joins elements either in single row by row across all columns 
* or joins elements in single column by column across all rows
#### create new value
##### apply vs map
###### <spam style="background-color:magenta"> 🔖 quick note : save map for mapper apply for cuntion </span>
###### <span style='background-color:magenta'>dataframe containing only one column</span>
* df.map(lambda x: " "  if cond else " ") 
* &emsp; it doesnt need to specifically naming the column 
* &emsp; reason : map Works only on Series. simple transformation task
* df['coln'].apply(lambda x: " "  if cond else " ") 
* &emsp; it <mark>does need to specifically naming the column</mark> 
* &emsp; reason : apply Works  Series and dataframe. complicated transformation task
###### differences comparison in general 
* Scope: <br>&emsp;map() → Series only; <br>&emsp;apply() → Series & DataFrame 
* Input types: <br>&emsp;map() accepts dict, Series, or callable; <br>&emsp;<mark>apply() accepts callable |function can be invoked using ()|only.</mark>
* Tip: <br>&emsp;transform each element in a Series with a simple function or mapping,for speed.<br>&emsp; Use apply() when you need more control or complex operations.
##### <span style="background-color:cyan;color:magenta;font-weight:bold">np.where[df['coln']=='x',True,False]&nbsp;</span> 
* boolean column  df['coln1']=np.where() 
* &emsp;purpose
* &emsp;&rarr; analysis -count 
* &emsp;&rarr; arguments acceptable 1:int 2:str :boolean 
##### <span style="background-color:cyan;color:magenta;font-weight:bold">df['coln'].mask(df['coln']=='x'&emsp;,o&emsp;)</span>
* &emsp;purpose
* &emsp;&rarr; analysis -count 
* &emsp;&rarr; arguments acceptable 1:int 2:str :boolean
##### <span style="background-color:cyan;color:magenta;font-weight:bold">np.where(df['c']=='x',1,0) vs .mask()</span>
* np.where() 2 returned values 
* df['col'].mask() 1 returnd value
* df['col'].mask() whatever doesnt meet the condition will remained intact </span>
##### entire new column | entire new row &emsp;
* df['new_coln']=['','',..]
* df.loc[n]=['','',..]&ensp;&emsp;&emsp;
* df.loc['x']=['','',..]&emsp;&emsp;
* df.loc vs df.iloc&emsp;&emsp;&ensp;
* &ensp;iloc is exlusively used forexisting data access and update
* &ensp;loc is reserved for creation of new rows 
## numeric symbols date arithmetic
### pd.to_numeric()
#### syntax
#### function
##### detailed explanantion 
##### <div style='background-color:magenta'>The pandas.to_numeric() function is used to <br>&emsp;convert an argument to a numeric type.<br> This function is particularly useful <br>&emsp;when you have a dataset with mixed data types and <br>&emsp;you want to ensure that all values are numeric. <br>The function has an <mark>errors parameter</mark> that can take the value 'coerce', <br>&emsp;which will replace any invalid parsing with NaN (Not a Number).</div>
### index 101 
#### store index of filtered values 
##### var=df[cond].index
#### index - column labels AKA column headers
#### index - row lables AKA row_number unique row id 
### order rank &ensp;<br>sort
#### df['coln'].rank()
##### syntax parameters
######  axis: 
* 0 or ‘index’ for rows and 
* 1 or ‘columns’ for Column.
######  method: Takes a string input<br>which tells pandas what to do with same values. 
* ‘average’, |default|
*  ‘min’,   
*  ‘max’, 
*  ‘first’,
*  ‘dense’) 
######  numeric_only:
* True - rank numeric values only 
* False- rank non-numeric values 
######  na_option: Takes 3 string input(
* ‘keep’, 
* 'top’, 
* ‘bottom’
######  ascending: 
* True -ascending
* False-descending
* output table with all possible combination of parameters for reference : differences highlighted for easy comaprison 
######  illustration table 
* table
* ![rank](./images/rank.png "System Diagram" )
#### df.sort_index()
##### 
#### df.sort_values()
##### syntax
##### memorizing rhyme -sort by key 
###### df.sort_values(by=['coln1','coln2',...])
##### parameters
###### <span style="background-color:magenta;color:cyan">key=function</span> 
* apply a function to the values before sorting
* example key=lambda col: col.str.lower()
* &emsp;&emsp;&rarr;convert a column's entry to lower case
* &emsp;&emsp;🔖<mark><b>function should be vectorized and expect a Series as input.</b></mark>
* &emsp;&emsp;🔖<mark><b>sort_values() only sort value instead of change its underlying data</b></mark> <br>&emsp;&emsp;&emsp;&emsp;<mark><bthus the output's case won't be converted to lowercases /b></mark>
###### <span style="background-color:magenta;color:cyan">axis=1column</span> 
* illustrations
* * explanation: conflicts may exist if a list of ascedning argument<br> has been passed, which is highlighted by a red dot : in this case<br> its better to sort by individual row instead of multiple rows at one <br>  
*   ![rank](./images/sortvaluesaxis.png "s" )
###### asending=[T,F] |T
* df.sort_values(by=['age',ascending=False])
* df.sort_values(by=['age', 'sales'],ascending=[False,True])
###### na_position='first'
* illustrations
* use case - very helpful for spottig na 
* ![rank](./images/sortvaluenaposition.png "s" )
###### inplace=F|T
* alter the original dataset or not 
###### kind 
* only affect single column opeartion 
#### sort_values() vs sort_index 
##### sort_values() based on values
##### sort_index() based on index
### comparison <br>operators
#### df['coln'] >=n
#### df['coln'] <= n
#### df['coln'] != n
#### df['coln'] == n |"*"
### range(start<br>&emsp; &emsp;&emsp;end)
#### df['coln'].between(n1,n2)
#### df['coln'].between(start,end)
### datetime&emsp;&nbsp;
#### df['coln'] >'2026-05-06'
#### notes📓
#### <ol><li>1. after >|greater than before < |less </li><li>2. date must be passed in string format</li></ol>
### query&emsp;&emsp;&ensp;
###### df.query("catg='x' and val=2")
# <div style="background-color:magenta;color:blue">  ![rank](./images/reshapetransform.png "s" )Reshape Join + | 1 &ensp;&nbsp;&nbsp;</div>
## check shape | overview of data
### df.info()
### df.shape
### df.describe()
### df.head()
### df.tail()
## multiindex
### to be updated
## <mark>Reshape swap col and row</mark>
###   <div style="border:dotted white;background-color:magenta">![rank](./images/pivot_regular_icon_205042.png "s" )</div>pivot_tb
#### pivot vs pivot_table()
##### &emsp; pivot()
###### &emsp;&emsp;&emsp;syntax 
###### parameters 
* 
* 
###### examples 
* example1
* example2
##### &emsp; pivot_table()
###### &emsp;&emsp;&emsp;syntax 
###### parameters 
* 
* 
###### examples 
* example1
* example2
#### which one is better : pivot_table
#### &emsp; reason 
##### # if index has duplicated entries then , pivot can't reshape 
##### pd.pivot_table(df,...) supports multiple indeces
#### &emsp; comparison example 
##### pd.pivot_table(df,)
##### df.pivot()
###   <div style="border:dotted white;background-color:magenta">![rank](./images/snowflake_melt_icon_137176.png "s" )</div>melt &emsp;&ensp;&ensp;<br>unpivot
#### syntax
##### parameters
###### 
###### 
###### 
#### melt and pivot and complementary functions 
#####   <div style="background-color:cyan;color:indigo;border:dashed blue ">![rank](./images/arrows-stretch-horizontal1_97917.png "s" )melt   converts wide → long.</div>
#####   <div style="background-color:magenta;color:white;border:dashed yellow ">![rank](./images/arrows-stretch-vertical1_98087.png "s" )pivot  converts long → wide</div> 
#### memorizing rhyme
##### meltdown cus its long 
##### pivot reduce width
#### use cases 
##### melt() for data cleaning and normalization. 
##### pivot() for summarizing or creating cross-tab style tables.
###   <div style="border:dotted white;background-color:magenta">![rank](./images/stack_overflow_stackoverflow_apps_platform_icon_176045.png "s" )</div>~unstack
#### ~ df.stack() |stack it up 
##### syntax 
##### example1
##### example2
#### ~ df.unstack() |unstack spread out
##### stack unstack
###   <div style="border:dotted white;background-color:magenta">![rank](./images/table_freeze_column_regular_icon_204872.png "s" )</div>explode 
#### similar to the excel -data -text to columns using delimiter comma 
#### two methods 
##### method 1 sereis 
###### df['coln'].explode()
##### method 2 dataframe 
###### df.explode('coln')
#### table
* illustrations
*   ![rank](./images/explodeseriesdataframe.png "s" )
###   <div style="border:dotted white;background-color:magenta">![rank](./images/addtabfileinterfacesymbol_79920.png "s" )</div>crosstab
#### essential function :crosstab <mark>frequency table<mark>
#### why its called a crosstab
##### A crosstab (short for cross-tabulation) is a<span style="background-color:magenta"> table used in statistics</span> <br>
##### display the relationship between two or more <mark>categorical variables.</mark>
#### parameters
##### index | columns
###### index 
* specifies values to groupby in the rows 
* &emsp;<span style="background-color:magenta">column(s) whose unique values will be used to form the rows</span> <br>of the resulting cross-tablulation 
* it accepts array-like, series , or list of array/sereis
 &emsp;&rarr;it has <span style="background-color:red;color:black">hiearchy</span> - the first index enjoys the highest priority
###### columns 
* &emsp;&rarr;it has <span style="background-color:red;color:black">hiearchy</span> - the first column enjoys the highest priority
###### illustration 
*   multi-index index row labels vs columns labels 
*   ![rank](./images/crosstabmultiindex.png "s" )
###### index columns -choosing 
* index
*  &emsp;&rarr;first think of the structure how many layer of indeces are needed
*  &emsp;&rarr;second =what's the priority struture which index should be the primary 
* &emsp;&emsp; which should be the secondary and so on 
* &emsp;&emsp; output of total number of rows are determined by the product 
* &emsp;&emsp; of the number of  unique values in each column eg :2 *3=6 2*2=4
* columns 
*  &emsp;&rarr;third determining columns - what catagorical values needs to be counted as frequency  
##### values | aggfunc
###### def 
* array of values to aggregate according to factors , Requires aggfunc 
* it accepts array like values and its optional 
###### usecase
* groupy reahspe is needed
* return max    top performer 
* return minim  bottom performer
* calculate sum |mean|mode
* which customer has order the largest amount
###### illustration
* single aggfunc|by default 1 agg won't have label
*   ![rank](./images/crosstabvalueagg.png "s" )
* mutiple aggfunction |func as labels to avoid confusion
*  ![rank](./images/crosstabaggfunc.png "s" )
##### rownames | colnums
###### those two parameters are used to rename the output labels 
* len must match  
* illustrations
*   ![rank](./images/crosstabcolname.png "s" )
##### margins | margin_names 
###### means subtotal on the marginal column
* True add one subtotal column
* False not adding
* illustration
*   ![rank](./images/crosstabmargin.png "s" )
###### means subtotals  on the marginal column and rows 
###### as that of a margin of a tabular frame||
##### dropna
###### remove na
##### normalize
###### index&emsp;&nbsp;&nbsp;|-each row
###### columns |-each column
###### True&emsp;&emsp;|-all values
###### illustration
* table
*   ![rank](./images/crosstab_normalize.png "s" )
#### use case
##### 1 
##### 2
##### 3
## groupby pivot_table crosstab summary
### commonality
#### all can apply aggfunc
##### parameter aggfuc pivot_table | crosstab
##### chained aggfunc  df.groupby('coln_catagorical_values')['coln_numerical_value'].agg()
### differences 
## <mark>Reshape reducing rows</mark>
###  <div style="border:dotted white;background-color:cyan">![rank](./images/software-scale-expand_97712.png "s" ))</div>sample
#### definition 
##### subset
#####  used to extract a random <mark>subset</mark> of rows or columns, <br>&emsp;&emsp;which can be useful for various data analysis tasks, such as <br>&emsp;&emsp;testing, validation, or exploratory data analysis.
#### example 
##### fractals dragon - the shape remains identical 
#### syntax
##### sample(n=n, or frac=None) 
###### major Parameters
* n    number of rows 
* frac fraction 
*  <mark>n vs frac</mark> can't be used together
* axis 
* &emsp; 1 : columns entire rows sample in certain columns
* &emsp; 0 : rows across all columns
######  <span style="background-color:magenta">random_state<mark> &emsp;=n </mark>&emsp;</span>
* &emsp;&emsp;n must be identical in the sampled subsets different seed(number|n) <br>&emsp;&emsp;returns different sample subsets
*   ![rank](./images/samplerandomstate.png "s" )
###### <span style="background-color:magenta">weights <mark></mark></span>
* purpose
* &emsp;This allows you to assign probabilities to rows, 
* &emsp; ensuring <mark>some rows are more likely to be selected than others.</mark>
* how 
* fisrt - assign weights to each row by creating a new column
* &emsp;- using 1: df['weights']=df.map(mapper_dictionary)|map(lambda condition)
* &emsp;&emsp;2: df['weights']=df.apply(lambda x: 5 if x == 1 else 1)
* &emsp;&emsp;&rarr;lambda x ： returned value if condition else returned value 
* &emsp;two call sample method with weights parameter 
* &emsp;- df.sample(n=2, weights='weights',)
###### ignore_index If True, the resulting index will be labeled 0, 1, …, n - 1.
###### <span style="background-color:magenta">replace </span><br>&emsp;bool, default False :Allow or disallow sampling of<br>&emsp;<mark>the same row more than once.</mark></span>
###   <div style="border:dotted white;background-color:magenta">![rank](./images/groupby1.png "s" ))</div>groupby
#### df.groupby('cat_coln')['val_coln'].mean() |single numeric column
#### df.groupby('cat_coln').mean() |all numeric columns
#### df.groupby('cat_coln').['val_coln'].agg(['mean','sum',..]) |mul agg 
#### df.groupby('cat_coln').['val_coln'].apply()
###   <div style="border:dotted white;background-color:magenta">  ![rank](./images/Cut_40922.png "s" )</div>agg()
#### single column |df single function
##### df.agg('sum')
##### df['coln'].agg('sum')
#### single column|df multiple functions 
##### df.agg(['sum', 'min'])
##### df['coln'].agg(['sum', 'min'])
#### multiple columns multiple functions 
##### df.agg({'A': ['sum', 'min'], 'B': ['min', 'max']})
##   drop column|index row<br>&emsp;&emsp;&emsp;add new column | row
###   <div style="background-color:green">![rank](./images/plus_grid_icon_251996.png "s" )</div>add.
#### col
##### df['coln_new']=['','',..] |  ="x"
#### row
##### df.clo[n,'coln']=['','',..] |  ="x"     integer based index -row label
##### df.clo['x','coln']=['','',..] |  ="xx"  string based index -row labels
### <div style="background-color:red">![rank](./images/Cut_40922.png "s" )</div>drop
#### <div style="background-color:beige;border:double white">![rank](./images/vertical-split_117508.png "s" )</div>
##### syntax
##### &emsp;df.drop(columns=['x,'y',..])
##### drop columns by passing column headers in stringed list to the parameter <mark>columns=</mark>
#### <div style="background-color:purple;border:double purple">![rank](./images/horizontal-split_117626.png "s" )</div>
##### syntax
##### &emsp;df.drop(index=['x,'y',..]) 
###### argument passing in comment
###### if index is string value based, then the arguments shall be wrapped in <br>quotation marks prior to the passing in 
##### &emsp;df.drop(index=[0,1,.....])
###### argument passing in comment
###### if index is numerical value based, then the arguments<br> should be passed in in the integer datatype
##### drop index by passing row index in stringed list or integer datatype list to the parameter <mark>index=</mark>
#### df.drop(index=[])
##   <div style="background-color:cyan">![rank](./images/table_cell_merge_icon_236475.png "s" )</div>Join&emsp;&nbsp;
### <div style="background-color:cyan">![rank](./images/table_cell_merge_icon_236475.png "s" )</div>Join 
####  (index_based) can be igonored
####  stick to merge which more flexible and diversified 
####  its error prone to use join - as index can be messy
####  prohibited 
##### don't use join&rarr;Use merge
##### <div style="background-color:white">![rank](./images/73031prohibited_109509.png "s" )</div>
### <div style="background-color:cyan;color:red;border:dashed blue">Merge  (flexible join+) best choice<br>&nbsp;inner&emsp; left &emsp;right &ensp;&nbsp;outer &emsp;full<br>![rank](./images/inner_join_icon_216471.png "s" )![rank](./images/left_join_icon_216523.png "s" )![rank](./images/right_join_icon_216521.png "s" )![rank](./images/outer_join_icon_216522.png "s" )![rank](./images/full_join_icon_216472.png "s" )</div>
#### syntax 
##### parameters
###### how=''
* how="left",'right' similar to vlookup 
* how='inner' intersection 
* how='outer' all
###### on=' '&nbsp;
* on='coln' only applies when two dataframes<br> that share the identical column header name
* lefton='coln_df1' righton='coln_df2' <br>two dataframes have different column header names
#### most used 
#####   <div style="background-color:white;color:indigo;border:double blue">![rank](./images/category-add-button_icon-icons.com_71724.png "s" )</div>left join&ensp;&nbsp;   |
###### add extra data to enrich and provide more information  based on left df's unique index similar to vlookup 
###### either from another workbook or from a database 
###### use cases 
* get price 
* get stock
* get product code
* get reference photo 
#####   <div style="background-color:yellow;color:indigo;border:double blue">![rank](./images/shape_intersect_regular_icon_204231.png "s" )</div>inner join&nbsp; 
###### intersection: for excluding values that's not mutually inclusive 
###### use cases 
* get the employee that works on both A project and B project 
* get the employee that is absent on both A event and B event
* get the product list that customer ordered in A order and B order
* 
#####    <div style="background-color:black;color:indigo;border:double blue">![rank](./images/augmentedreality-7_111378.png "s" )</div>outer join&nbsp; 
###### all the crossed index -gain a view of the full picture |panoranic view 
###### use cases 
* get all individual departments and form a complete compnay file
* get all products across every bu
### <div style="background-color:yellow;color:indigo;border:double blue">pd.concat(df1,df2,..axis=0|1)<br>![rank](./images/horizontal_menu_burger_icon_227407.png "s" )![rank](./images/horizontal_menu_burger_icon_227407.png "s" )1![rank](./images/3844436-hamburger-menu-more-navigation-vertical_110316.png "s" )![rank](./images/3844436-hamburger-menu-more-navigation-vertical_110316.png "s" )2</div>
#### &emsp;All in one overview
##### <span style="background-color:red;color:cyan">pd.concat ([df1,df2,...]) stacking ver|hor</span>
##### &emsp;comments: 
##### &emsp;dfs should be passed in using a list
#### syntax
#### &emsp;&rarr;pd.concat(df1,df2,..,axis=0)
#### &emsp;&rarr;axis=1 columns -vertical join fatter
#### &emsp;&rarr;axis=0 rows    -horizontal join thinner
##### ignore_index=
###### True- reindex in sequential order the newly contacted df will adopt the index that start from the next of the last index of the first df
###### False- original index of concated df will be kept for reference 
#### vertical then column number and column header names and
#### their orders must be identical
#### horizontal then the indeces must be identical or the concate
#### won't be of any referential value 
# <div style="background-color:white;color:black">![rank](./images/datetime.png "System Diagram" )datetime Date+Time&ensp;</div>
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
# pd. summary
## option | set option
### pd.set_option('display.max_rows',None)
### pd.set_option('display.max_columns',None)
### pd.set_option('display.width',None)
### pd.set_option('display.max_colwidth',None)
### pd.options.display.max_rows 
### pd.options.display.min_rows   
### pd.options.mode.copy_on_write = True
### pd._config.localization.set_locale('', locale.LC_TIME):
## create df
### pd.Series 
### pd.DataFrame
### pd.read_
#### pd.read_csv
#### pd.read_excel
#### pd.read_html
#### pd.read_sql
#### pd.read_json
## reshape
### pd.crosstab()
### pd.melt
### pd.merge
### pd.concat
### pd.qcut()
## single catagory
### df.update(df1)
### pd.reindex
### pd.get_dummies()
### <mark>pd.grouper</mark>
### pd.to_numeric()
## datetime
### pd.DateOffset(  months =1)
### pd.date_range()
### pd.to_datetime(  )
### pd.to_timedelta()
# DS summary
## machine learning
### normal distribition 
#### charateristics 
##### 1std:68 &emsp;2std:95 &emsp;3std:99.7 
##### symmetric shape bell curved
#### why is it needed
##### find out central tendency mode mean median
##### to spot outliers 
##### models must be normally distributed to yeild reliable speculations 
##### non normal model can conatin outliers and skewness 
#### how to determine whether its normal or not
##### visuals<br>qq dist
###### stats.probplot()
###### seaborn
* sns.boxplot()
* sns.histplot() | sns.kdeplot() 
##### p_value &rarr; <br>probability 
* stat, p = shapiro(data) | p>0.05 Normal
* stat, p = normaltest(data)  | p>0.05 Normal
* <mark>result = anderson(data) </mark> to be continued
* statistic, pvalue = chisquare(data) | p>0.05 Normal
* statistic, pvalue = lilliefors(data) | p>0.05 Normal
* statistic, pvalue = jarque_bera(data) | p>0.05 Normal
* statistic, pvalue = kstest(data, 'norm') | p>0.05 Normal
##### <mark>&emsp;🔖Notes&emsp;</mark>
* sample size needs to be large >2000
* 
##### which method to use 
###### table comparison
###### <table border="1" class="dataframe"><thead><tr style="text-align: left;padding:5px"><th width="200">TEST Methods</th><th width="200">Use Case</th><th width="150">Data Size</th></tr></thead><tbody><tr><td>Shapiro-Wilk</td><td>General purpose</td><td>Small to Medium</td></tr><tr><td>Kolmogorov-Smirnov</td><td>Known parameters</td><td>Large</td></tr><tr><td>Anderson-Darling</td><td>More sensitive than <br>Kolmogorov-Smirnov</td><td>All sizes</td></tr><tr><td>Lilliefors</td><td>Estimated parameters</td><td>Small to Medium</td></tr><tr><td>D'Agostino's K2</td><td>Skewness and Kurtosis</td><td>Medium to Large</td></tr><tr><td>Jarque-Bera</td><td>Skewness and Kurtosis</td><td>Medium to Large</td></tr><tr><td>Pearson's Chi-Square</td><td>Binned data</td><td>Any size</td></tr></tbody></table>
#### use case 
##### linear regression 
##### time series forecast
## Data 
### numbers
#### types
##### integer 
##### floats
###### floating point number
##### complex
###### real+imaginary
#### mathmetical operation 
##### * + -  / // %  
##### np.sqrt np.pi np.exp np.linalg 
##### sympy calculus
##### statsmodels 
##### statistics 
###### abs
###### round 
###### max 
###### min
###### avg mean mode
### strings<br>|immuatble|
#### split&join
##### split
###### split |rsplit |lsplit 
###### splitlines
###### partition 
##### join
###### +
* df['coln1']  +  df['coln2']
###### str.cat()
* df['coln1'].str.cat(df['coln2'])
###### ''.join()
* '-'.join(df['coln1'])
* str*5 repetition by 5 times 
#### case | comments
###### case
* upper lower capital title 
* swapcase casefold
###### comments
* single line -single quote double quote 
* multiple lines -triple quotes
#### strip&replace
#### index&slice
#### find&count
##### len(str)
##### find | index 
###### find substring in string to return index 
###### difference in how they handle exception - if not exist index will return an error 
##### count
###### count occurances of substring within string 
### conversion 
#### pd.to_numeric()
#### str(number)
#### int(string)
### string format 
#### place holder
##### f"{}"
#### format method
##### apply(lambda  x: 'prefix{:.2f}suffix'.format( processing  ))
##### apply(lambda  x: 'prefix{:.2f}suffix'.format( x*n ))
## frames
#### index 
##### indexrow
###### AKA row identifiers 
###### AKA row label
##### columns.
###### AKA column headers
###### AKA column label
#### series 
##### equivalent to excel column 
##### convert to dataframe .to_frame()
##### series vs list vs array
###### list -non vectorized operation for loop must used or apply | mapis needed 
###### arry -vectorized operation supported
###### series -vectorized+index 
###### seires index 
* integer  -default
* string   - catagorical data 
* datetime -stock | business
##### series index 
###### integer&emsp;: acess df.loc[n]=[]
* all no columns is needed 
* [n ,  'coln ']=[] specific column then argument is needed 
###### string&emsp;&nbsp;&nbsp;: acess df.loc['str']=[]
* all no columns is needed 
* ['str' ,  'coln ']=[] specific column then argument is needed 
###### datetime&nbsp;: acess df.loc['datetime',]
* all no columns is needed 
* ['str' ,  'coln ']=[] specific column then argument is needed 
* datetime is also considered string type by default , as it has 
* &emsp;fixed format : &emsp;'y-m-d h:m:s'  |&emsp;'y/m/d h:m:s' |&emsp;'y/Mon/d h:m:s' 
* however, the target column must first be converted into datetime object type using pd.to_datatime(df['date'])
#### dataframe 
##### composed of multiple series 
## visualization 
### pandas 
#### df.plot(kind='')
### matplotlib + seaborn
#### plt
##### plt.plot(x,y)
#### sns
##### mul-plot
###### sns.pairplot()
##### sns.joinplot()
##### mon-plot
###### sns.displot()
###### sns.replt()
###### sns.catplot
######
###### sns.heatmap(df.corr())
### plotly dash 
### sympy 
#### equation based
### manim 
#### equation based 
#### line scatter
#### polar 
#### bar 
#### pie