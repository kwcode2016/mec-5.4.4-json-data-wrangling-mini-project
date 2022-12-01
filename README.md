# mec-5.4.4-json-data-wrangling-mini-project

## Exploring World Bank Projects stored as JSON with Pandas

### 1. Find the 10 countries with most projects

Grouping by country and counting how many projects each country has. Sorting by number of projects and displaying top 10 countries.

### 2. Find the top 10 major project themes (using column 'mjtheme_namecode')

In the column 'mjtheme_namecode', each cell has multiple values for each row.
Using json_normalize, extracting each value from each row and creating a new dataframe 'mjtheme_namecode_df'.
Notice that 'mjtheme_namecode_df' has many names that are blank. 


### 3. In 2. above you will notice that some entries have only the code and the name is missing. Create a dataframe with the missing names filled in.

As noticed in the last section, many names are missing. 
Created a reference dataframe 'mjtheme_namecode_list_df' which is the Reference Dataframe (showing what name each code is). 

I do recognize I didn't fully check  each code number has different variants of name. But I did check a number of them and found the name to be the same for 1 code number.

To fill in the missing names, I did a pd.merge (left join method) of 'mjtheme_namecode_df' and 'mjtheme_namecode_list_df' which will fill in a new column with all the names filled in.

I do recognize that I didn't check if each existing name matched fully to the new fully filled in col.

Afterwhich, I deleted the old column with missing names and renamed the new column to 'name'
