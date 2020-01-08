# csvmerge
Parse CSV files and stack them by their matching columns.

## Requirements
pandas 

## Example

```txt
$ csvlook file1.csv
| f1 | f2 | f3 | f4 |
| -- | -- | -- | -- |
|  0 |  1 |  2 |  3 |
|  4 |  5 |  6 |  7 |

$ csvlook file2.csv
| f1 | f4 | f5 | f6 | f7 |
| -- | -- | -- | -- | -- |
| a  | b  | c  | d  | e  |
| f  | g  | h  | i  | j  |
| k  | l  | m  | n  | o  |

$ python3 csvmerge.py --delimiter=',' file1.csv file2.csv
Done.

$ csvlook out.csv
| f1 | f2 | f3 | f4 | f5 | f6 | f7 |
| -- | -- | -- | -- | -- | -- | -- |
| 0  |  1 |  2 | 3  |    |    |    |
| 4  |  5 |  6 | 7  |    |    |    |
| a  |    |    | b  | c  | d  | e  |
| f  |    |    | g  | h  | i  | j  |
| k  |    |    | l  | m  | n  | o  |
```

## Usage

```txt
$ python3 csvmerge.py --help
usage: csvmerge.py [-h] [--delimiter DELIMITER] [--encoding ENCODING]
                   [--output OUTPUT]
                   input_files [input_files ...]

Parse CSV files and stack them by their matching columns.

positional arguments:
  input_files           List of csv-files, separated by comma.

optional arguments:
  -h, --help            show this help message and exit
  --delimiter DELIMITER
                        CSV-delimiter (default: ';')
  --encoding ENCODING   Encoding of CSV-files (default: 'utf-8')
  --output OUTPUT       Output-file (default: 'out.csv')
```
