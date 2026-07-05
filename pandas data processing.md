# pandas<br>processing
### stringtxt
#### filter and  info&ensp;&nbsp;
##### df['coln'].str.len()
##### <span style="background-color:cyan;color:magenta;font-weight:bold">df['coln'].str.count('x')</span>
###### Count the occurrences of a specific substring in each string of a Series
###### eg<div >sentences = pd.Series([&emsp;'Python is fun', <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;&emsp;'I love Python', <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;&emsp;'Python programming is powerful'&emsp;])<br>python_counts = sentences.str.count('Python')<br>print(python_counts)<br>output:1 2 2 </div>
##### df['coln'].str[n1] |indexing|
##### df['coln'].str[n1:n2] |slicer|
##### <span style="background-color:cyan;color:magenta;font-weight:bold">df['coln'].str.cat(sep)</span>
###### concatenate strings in a Series or Index with a specified separator. <br>It can handle missing values and allows flexible concatenation with other<br>Series, DataFrames, or list-like objects.
###### eg<div>s = pd.Series(['a', 'b', np.nan, 'd']) <br>t = pd.Series(['x', 'y', 'z'], index=[0, 2, 3])<br>result = s.str.cat(t, join='outer', na_rep='-')<br>output: ax , b- , -y , dz2</div>
##### df['coln'].str.startswith('x')
##### df['coln'].str.endswith('x')
##### df['coln'].str.conatins('x')
##### df['coln'].str.match('x')
##### df['coln'].str.strip()  |customizable|     
#### transformation
##### df['coln'].replace('old_str' ,'new_str')
##### df['coln'].str.upper()
##### df['coln'].str.lower()
##### df['coln'].str.capitalize()
### numeric <br> symbols
#### comparison <br>operators
##### df['coln'] >=n
##### df['coln'] <= n
##### df['coln'] != n
##### df['coln'] == n |"*"
##### df['coln'].between(n1,n2)
##### df['coln'] >'2026-05-06'
###### notes📓
###### <ol><li>1. after >|greater than before < |less </li><li>2. date must be passed in string format</li></ol>
##### df.query("catg='x' and val=2")
### na <br>duplicate
##### df['coln'].notna()
##### df['coln'].isna()
##### df['coln'].fillna()
##### df['coln'].dropna()
##### <span style="background-color:cyan;color:magenta;font-weight:bold">df.interpolate()</span>
######  fill missing values (NaN) in a DataFrame or Series using various interpolation techniques. 
###### eg<div >time_index = pd.date_range('2023-01-01', periods=5, freq='D')data = [10, <span style="background-color:red;border:double white;padding:1px">&emsp;np.nan&emsp;</span>, 30,<span style="background-color:red;border:double white;padding:1px">&emsp;np.nan&emsp;</span>, 50]<br>df = pd.DataFrame(data, index=time_index, columns=['Value'])<br>df_interpolated = df.interpolate(method='time')<br>print(df_interpolated)<br>output:<br> 2023-01-01 <mark>|10.0|</mark> ,2023-01-02 <span style="background-color:red;border:double white;padding:1px">&emsp;20&emsp;</span> ,<br>2023-01-03 <mark>|30.0|</mark>, 2023-01-04 <span style="background-color:red;border:double white;padding:1px">&emsp;40&emsp;</span>,2023-01-05 <mark>|50.0|</mark></div>
##### df['coln'].drop_duplicates(keep)<span style="font-size:50px;background-color:blue">⤫</span>
##### df.duplicated(['coln1','coln2',..])<span style="font-size:50px;background-color:red">👁</span>