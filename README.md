# iglut

Look up tables in GTM can be very useful, but they can also be very tedious to create. This program can take any CSV or TSV file and create the necessary JSON file to import into GTM to create or update a lookup table.

## Install

This program requires [Node.js][node]. Once install use `npm` to install this program from the command line.

```shell
npm install -g import-gtm-lookup-table
```


## Usage

Running this program is quite simple. All it needs is a file in CSV or TSV format. Google Sheets and Microsoft Excel can both produce a CSV file. Note, the input file should only have two columns to match the lookup table in GTM.

```shell
iglut input.csv output.json 
```

This will read form the input.csv file and create/update the output.json file. The resulting JSON file then needs to be [imported into GTM][import].


## Advanced Usage

Additionally, the option to redirect stdin and stdout is present.

```shell
cat input.csv | iglut > output.json
```
If a header row is present in the input file, then the names of the columns in the header row will be used to generate the name of the lookup table and the input for the lookup table.

There are optional arguments to the program to override the default values.

-n <name>, --name <name>
    The <name> of the variable to create/update in GTM.

-i <value>, --input <value>
    Use this <value> as the input to match against the first column.

-d <value>, --default <value>
    Use this <value> as the default value to return with the input value does not match any rows in the first column.

# License

iglut is licensed under the [MIT Licence][license].

[node]: https://nodejs.org/
[import]: https://support.google.com/tagmanager/answer/6106997
[license]: https://github.com/keithws/iglut/blob/master/LICENSE
