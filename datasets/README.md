# Datasets directory

Please download the datatsets from this [link](https://web.utk.edu/~auerbach/HOWL.htm)
and include them is this directory.

The notebooks are designed to work with the CSV version of the datasets.
At the time these notebooks were created, the filenames were 
`Howell.csv`, `HowellTest.csv`, `Goldman.csv`.

The relevant notebook commands are:

`raw_data_howell = pd.read_csv("datasets/Howell.csv", header = 0, encoding= 'unicode_escape')`

`raw_data_howell_test = pd.read_csv("datasets/HowellTest.csv", header = 0, encoding= 'unicode_escape')`

`raw_data_goldman = pd.read_csv("datasets/Goldman.csv", header = 0, encoding= 'unicode_escape')`

However, if you decide to use a different filename just 
modify the filename shown in the above coammands.