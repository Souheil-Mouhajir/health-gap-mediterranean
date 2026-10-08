# Closing the health gap across the Mediterranean, 1952 to 2025

This project compares life expectancy at birth in five **North African** countries (Morocco, Algeria, Tunisia, Libya, Egypt) and five **Southern European** countries (Spain, Portugal, Italy, Greece, France) from 1952 to 2025. It also tests whether income followed the same path. The data is the **Gapminder Fast Track** dataset.

Author: Souheil Mouhajir, The George Washington University, Elliott School of International Affairs. October 2026.

[View the rendered report]()

## Findings

- The median life expectancy gap between the two groups was 24.6 years in 1952. It fell to a low of 7.5 years in 2002 and was 8.9 years in 2025.
- Most of the convergence happened between 1977 and 1987, when the gap fell from 17.2 to 9.6 years.
- Every North African country gained at least 28.6 years over the period. Southern European gains ranged from 11.3 years (Greece) to 21.7 years (Portugal). Algeria gained the most, at 39.1 years.
- No North African country reached the lowest Southern European level in 2025. Algeria, the highest in North Africa at 76.4 years, is 4.9 years below Greece.
- Income did not drive the convergence. Indexed to 1952 = 100, median GDP per capita reached 557 in North Africa and 918 in Southern Europe. Egypt's index (935) matched Spain's (937), yet Egypt has the lowest life expectancy of the ten countries, at 70.4 years.
- Group means with 95 percent confidence intervals never overlap at any of the 16 time points.

## Charts

The report has a dot plot of 2025 values and a slope chart of 1952 against 2025. It also has a paired dot chart sorted by gain and small multiples on a shared y scale. Two normalized views follow: GDP per capita indexed to 1952 on a log scale, and the annual rate of change in median life expectancy. Three extensions close the report. The first plots group means with 95 percent confidence intervals. The second is an interactive **Plotly** chart of income against life expectancy, animated by year. The third is an embedded **Flourish** bar chart race.

## Repository contents

| File | Content |
| --- | --- |
| `comparison_charts.qmd` | Quarto source of the report |
| `comparison_charts.ipynb` | Same analysis as a Jupyter notebook |
| `comparison_charts.html` | Rendered report, self-contained |
| `theme.scss`, `theme-dark.scss` | Light and dark themes for the HTML output |
| `requirements.txt` | Python packages with pinned versions |
| `data/lex.csv` | Life expectancy at birth, ten countries, 1950 onward |
| `data/gdp_pcap.csv` | GDP per capita, PPP, constant 2021 international dollars, ten countries, 1950 onward |

## Data

Both series come from the Gapminder Foundation's Fast Track dataset, published as [open-numbers/ddf--gapminder--fasttrack](https://github.com/open-numbers/ddf--gapminder--fasttrack) on GitHub. Life expectancy is `lex` version 15 (April 5, 2026). GDP per capita is `gdp_pcap` version 32 (September 20, 2025). The analysis keeps one year in five from 1952 to 2022, plus 2025, for 16 time points.

The `data` folder holds a snapshot of both files cut to the ten countries. Gapminder revises recent years between versions, so a fresh download may give slightly different 2025 values.

## Reproducing the report

The notebook reads the snapshot in `data/` and downloads the files from GitHub only when the snapshot is missing, so rendering works offline. The steps below need Python 3 and [Quarto](https://quarto.org).

```bash
pip install -r requirements.txt
quarto render comparison_charts.qmd
```

The notebook also runs on its own in Jupyter with `jupyter notebook comparison_charts.ipynb`. The Flourish chart race is an embedded iframe and needs an internet connection to display.

## Source

Gapminder Foundation, Fast Track dataset, `lex` v15 (April 5, 2026) and `gdp_pcap` v32 (September 20, 2025).
