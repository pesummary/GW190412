## GW190412

This repository holds the static html pages generated with the
[publically available data](https://dcc.ligo.org/public/0163/P190412/008/posterior_samples.h5)
using the [pesummary](https://lscsoft.docs.ligo.org/pesummary/) python package.
This repository acts as an accompaniment to the [pesummary paper](). The file
which was used to generate these webpages can be downloaded with python by
running the following,

```python
>>> import requests
>>> data = requests.get("https://dcc.ligo.org/public/0163/P190412/008/posterior_samples.h5")
>>> with open("posterior_samples.h5", "wb") as f:
...     f.write(data.content)
>>>
```

All command lines that were used to generate the webpages can be found on the
webpages themselves under the 'Downloads' tab. Details of the environment which
was used to generate the webpages can seen under the 'Version' tab.

This result file stores the combined PHM samples under the label 'combined'. As
the comparison plots also use this label, we modify the combined PHM samples
label before generating the summarypages with the following command line:

```bash
$ summarymodify --webdir ./ --samples posterior_samples.h5 --labels combined:combinedPHM --overwrite
```
