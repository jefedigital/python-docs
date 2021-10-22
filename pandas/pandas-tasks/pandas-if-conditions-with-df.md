# Pandas - IF conditions with df

[https://datatofish.com/if-condition-in-pandas-dataframe/](https://datatofish.com/if-condition-in-pandas-dataframe/)

df\['name\_match'] = df\['First\_name'].apply(lambda x: 'Match' if x == 'Bill' else 'Mis-Match')
