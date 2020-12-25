# Pandas

## Getting started:

To use pandas, you'll typically start with the following line of code.

```
import pandas as pd
```

## Creating data

There are two core objects in pandas: the DataFrame and the Series.

### DataFrame

A DataFrame is a table. It contains an array of individual entries, each of which has a certain value. Each entry corresponds to a row (or record) and a column.

For example, consider the following simple DataFrame:

```
pd.DataFrame({'Yes': [50, 21], 'No': [131, 2]})
```