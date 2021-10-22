# Pandas - fix labels

import re

df.columns = \[re.sub(' ', ' ', x) for x in df.columns]

df.columns = \[re.sub('-|\ ', '\_', x) for x in df.columns]

df.columns = \[re.sub('\_\_', '\_', x) for x in df.columns]

df.columns = \[re.sub('\_\_', '\_', x) for x in df.columns]

df.columns = \[re.sub('-|\\,|\\(|\\)', '', x).lower() for x in df.columns]

lower-case, replace spaces with underscores
