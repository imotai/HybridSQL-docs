# Data types

## Numeric Types

| Type     | Bytes   | Range                                                        |
| :------- | :------ | :----------------------------------------------------------- |
| BOOL     | 1 byte  | (-128，127)                                                  |
| SMALLINT | 2 bytes | (-32 768，32 767)                                            |
| INT      | 4 bytes | (-2 147 483 648，2 147 483 647)                              |
| BIGINT   | 8 bytes | (-9,223,372,036,854,775,808，9 223 372 036 854 775 807)      |
| FLOAT    | 4 bytes | (-3.402 823 466 E+38，-1.175 494 351 E-38)，0，(1.175 494 351 E-38，3.402 823 466 351 E+38) |
| DOUBLE   | 8 bytes | (-1.797 693 134 862 315 7 E+308，-2.225 073 858 507 201 4 E-308)，0，(2.225 073 858 507 201 4 E-308，1.797 693 134 862 315 7 E+308) |

------

## Date&Timestamp Types

The date and time data types for representing temporal values are `DATE` and `TIMESTAMP`

| Type      | Bytes | Range                   | Format          |
| :-------- | :---- | :---------------------- | :-------------- |
| DATE      | 4     | 1900-01-01 ~ 9999-12-31 | YYYY-MM-DD      |
| TIMESTAMP | 8     |                         | YYYYMMDD HHMMSS |

------

## String Type

| Type   | Bytes | Range |
| :----- | :---- | :---- |
| STRING | 4096  |       |


