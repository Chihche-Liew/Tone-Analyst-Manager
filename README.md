# Replication Package: Managers' Use of Humor on Public Earnings Conference Calls

This repository contains the replication package for the paper's measurements of tone_analyst and tone_manager:

**Call, A. C., Flam, R. W., Lee, J. A., & Sharp, N. Y. (2023). Managers' use of humor on public earnings conference calls. *Review of Accounting Studies*, 28(4), 1234-1268.**

## Overview

This replication package reproduces the tone calculation methodology used in the original study to analyze managers' and analysts' sentiment on earnings conference calls. The analysis focuses on extracting and measuring positive and negative sentiment from earnings call transcripts.

## Data Sources

The analysis relies on the following data sources:

- **Transcript Data**: 
  - `wrds_transcript_detail.pkl` - Detailed transcript metadata from Capital IQ
  - `transcript_ea.pkl` - Earnings call transcript components from Capital IQ
- **Sentiment Dictionary**: 
  - `Loughran-McDonald_MasterDictionary_1993-2024.csv` - Sentiment word dictionary from [Loughran and McDonald's website](https://sraf.nd.edu/loughranmcdonald-master-dictionary/)

## Methodology

The tone calculation process follows these key steps:

1. **Data Preprocessing**: Clean and standardize transcript text by removing special characters and converting to lowercase
2. **Component Separation**: Distinguish between manager statements (type 4) and analyst statements (type 3)
3. **Sentiment Analysis**: Apply the Loughran-McDonald dictionary to count positive and negative words
4. **Tone Calculation**: Compute tone scores as (positive_words - negative_words) / total_sentiment_words

## Files

- `tone_calculation.ipynb` - Main Jupyter notebook containing the complete replication code
- `README.md` - This documentation file

## Requirements

```python
pandas
numpy
duckdb
tqdm
datetime
collections
re
```

## Usage

1. Ensure all required data files are in the project directory:
   - `wrds_transcript_detail.pkl`
   - `transcript_ea.pkl` 
   - `Loughran-McDonald_MasterDictionary_1993-2024.csv`

2. Run the Jupyter notebook `tone_calculation.ipynb` cell by cell

3. The final output will be saved as `tone.pkl` containing transcript-level tone measures for both managers and analysts

## Output

The final dataset includes:
- `transcriptid` - Unique identifier for each earnings call
- `tone_manager` - Sentiment tone score for manager statements
- `tone_analyst` - Sentiment tone score for analyst statements

## Citation

If you use this replication package, please cite the original paper:

```bibtex
@article{call2023managers,
  title={Managers' use of humor on public earnings conference calls},
  author={Call, Andrew C and Flam, Rachel W and Lee, Joshua A and Sharp, Nathan Y},
  journal={Review of Accounting Studies},
  publisher={Springer}
}
```

## License

This replication package is provided for academic research purposes. Please refer to the original paper and data source terms of use for any commercial applications. 