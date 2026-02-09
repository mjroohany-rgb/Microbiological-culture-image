================================================================================
               README - Supplementary Colony Count Data
                      Automated Colony Counter Project
================================================================================

This README file explains the structure and content of the accompanying Excel
workbook "Supplementary_Colony_Count_Data.xlsx". The workbook contains raw and
processed data from validation experiments comparing manual and automatic colony
counting methods.

--------------------------------------------------------------------
1. WORKBOOK STRUCTURE
--------------------------------------------------------------------
The Excel workbook contains three sheets:

  1. Raw_Data
  2. Averaged_Data
  3. Statistical_Summary

--------------------------------------------------------------------
2. SHEET DETAILS
--------------------------------------------------------------------

2.1 SHEET: "Raw_Data"
----------------------------------------
Contains all experimental data in a "long" format suitable for statistical
analysis.

COLUMNS:
  • Organism: Microorganism tested.
    - Mold & Yeast
    - Staphylococcus aureus
    - Total Plate Count
    - Escherichia coli

  • Dilution: Dilution level (1 = least diluted, highest colony density).

  • Replicate_ID: Identifier for the technical replicate (1, 2, 3, or 4).

  • Method: Counting method.
    - Manual: Standard human count (operator).
    - Automatic: Count from the developed image-based colony counter system.

  • Count: Number of colonies counted.

NOTES:
  • Manual counts have 4 replicates per dilution.
  • Automatic counts have 3 identical replicates per dilution (algorithm output
    is consistent for the same image).


2.2 SHEET: "Averaged_Data"
----------------------------------------
Contains summarized data with means and standard deviations for each combination
of Organism, Dilution, and Method.

COLUMNS:
  • Organism, Dilution, Method: As described above.

  • Mean_Count: Arithmetic mean of counts.
    - For Manual: Mean of 4 replicates.
    - For Automatic: Value of the first replicate (all replicates are identical).

  • Std_Deviation: Standard deviation of counts.
    - For Automatic: Always 0.00 due to identical replicates.

  • Number_of_Replicates: Number of replicates used to calculate the mean.

  • Note: Brief explanation of the calculation.


2.3 SHEET: "Statistical_Summary"
----------------------------------------
Provides a comparative analysis between Manual and Automatic counting methods.

COLUMNS:
  • Organism, Dilution: As described above.

  • Manual_Mean: Mean manual count (from Averaged_Data).

  • Auto_Mean: Automatic count (from Averaged_Data).

  • Absolute_Difference: Auto_Mean - Manual_Mean.
    - Positive value: Overcount by the automatic system.
    - Negative value: Undercount by the automatic system.

  • Relative_Difference_Percent: (Absolute_Difference / Manual_Mean) × 100%.
    - Expresses the difference as a percentage of the manual count.

  • Agreement_Level: Qualitative assessment based on Relative_Difference_Percent.
    - "Good"      : |Relative Difference| < 10%
    - "Moderate"  : 10% ≤ |Relative Difference| < 20%
    - "Poor"      : |Relative Difference| ≥ 20%

  • Note: Brief comment on the observed trend.

--------------------------------------------------------------------
3. IMPORTANT NOTES & INTERPRETATION GUIDELINES
--------------------------------------------------------------------

3.1 DATA INTEGRITY
  • Automatic counts are algorithmically consistent; hence, all replicates per
    image are identical.
  • Manual counts show natural human variation, reflected in non-zero standard
    deviations.

3.2 INTERPRETING AGREEMENT
  • "Good" agreement indicates the automated system performs comparably to a
    human operator for that specific organism and dilution.
  • "Poor" agreement, especially at high densities (Dilution 1), suggests the
    algorithm may require optimization for overlapping colonies or specific
    morphological features.
  • Very low manual counts (e.g., < 5 colonies) lead to high relative errors;
    these should be interpreted with caution.

3.3 USE OF DATA
  • This dataset is intended for:
      1. Validation of the automated colony counter system.
      2. Comparative error analysis.
      3. Further statistical testing if required (e.g., regression, Bland-Altman).

--------------------------------------------------------------------
4. ABBREVIATIONS
--------------------------------------------------------------------
  • Std_Deviation : Standard Deviation
  • Auto          : Automatic (image-based system)
  • Manual        : Human operator count (standard reference)

--------------------------------------------------------------------
5. CONTACT
--------------------------------------------------------------------
For questions regarding this dataset, please refer to the main thesis document
or contact the author.

================================================================================
END OF README
================================================================================