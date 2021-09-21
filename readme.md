# SAS Programming for CLinical Trials

## Types of Clinical Trials

## Drug/Device developement process

- Basic Research > Non-clinical studies > Clinical Studies > New Drug application and Review > Approval and launch > Post marketing Surveillance (Phase 4)
    - `Phase I` - **Safety** in healthy (sample 10-20)
    - `Phase II` - **Effectiveness** and safety dose in **patients** (sample ~ 200)
    - `Phase III` - Safety and Efficacy **comparison** to other treatments (1000+) - more likely to detect rate side effects
    - `Phase IV` - Post-marketing surveillance

- **Single Blind** - patients do not know
- **Double Blind** - Neither patients nor doctors know
- **Tipple blind** - Even the statisticians do not know, nor patients nor doctors

- Device Approval process
    - `Class 1` - surgical instruments
    - `Class 2` - infusion pumps motorized wheel chairs
    - `Class 3` - highest risk devices: heart valves, implantations

## Regulations
- **Fedral laws** 
    - `21 CFR (Code of fedral regulations) - Part II`, electronic records and signatures to FDA
        - The person must be qualified to do your work. Must have a degree
        - Programming must be validated - compared with another statistical programmer
        - Must have system security - Not every person can access the data
        - Change control procedures for SAS programming - Versions of the program will be documented. It should be documented why there are 2 versions of the program after finalized
    - `HIPA` - Only a patient's **initials** and **date of birth** can be collected

- **Fedral Guidelines** (eCTDs - Electronic Common Technical Documents)
    - `Study data standards` - Standards of Electronic Submissions of data to FDA
        - Data must be submitted in `SDTM` and `ADaM` formats
    - Other
        - CDER Common Data Standards Issues Document
        - CDER Data Standards Program

- **Industry Regulations** and Standards (`ICH` - International Conference on Harmonization, `CDISC` -Clinical Data Interchange Standards Consortium ) 
    - ICH is a global organization that provides standard values for data
    - CDISC developes standards for the pharmaceutical industry
        - `ICH E3 - Structure and content` : of Clinical Study Reports - **Clinical study report for FDA submission** - deals with what must be the contents of these reports
        - `ICH E9 - Statistical principals` : for clinical trials - Statistical issues for the design and conduct of a clinical trial. For example intent to treat and safety populations
        - `ICH E6 - Good Clinical Practice`: Consolidated Guidance - Overall standards

## Raw Data > CDASH
- Operational Data Model (ODM)
    - Key feature is tracability for audit trail
    - XML-based
    - Archive and interchange metadata and data
    - Audit trail for 21 CRF Part II complaint - including email correspondence

- Define XML
    - Variable attributes
    - Controlled Terminology
    - Computational Models

The Raw data is transported from clinical sites and labs in ODM and XML formats constitute CDASH whcih is then converted to SDTM (tabulation) and ADaM (ready for analysis) formats for submission package. SAS V5 is the open standard required for data submission - It is independent and can also be read by other softwares

## Clinical report (CRF) forms
Clinical Report Forms - 10 types
    - Demographics
    - Concomitant or prior meds
    - Medical history
    - Laboratory
    - Adverse Event
        
    - Endpoint/event assessment
    - Clinicl enpoint committee
    - Study termination data
    - Treatment randomization data
        - Usually found with some Interactive Voice Response System (IVRS)- but maybe recorded in an electronic file as well. 
    - Quality of life data
        - SF-36 and SF-12 health survey for quality of life questionares

## SAS Programing Commands commonly used in Clincial Trials data
- **Import and Export clinical trials data**
    - `set`, `merge`
    - `libname`, `proc import/export`
    - `sas V5 (proc copy)`
- **Manage Clinical Trials Data**
    - `print`, `contents`, `freq`
    - `dictionary` using `sql`
- **Transform Clinical Trials Data**
    - `do loops`, `proc transpose`
    - `retain`
    - `categorization`
    - functions (`input`, `put`, `date`)
    - `locf`, `bocf`, `wocf`
    - Change from baselne, percent change
- **Statistical Procedures**
    - `freq`, `univariate`, `means`, `summary`
    - `freq` for categorical data
    - `ttest`
    - `extract`
- **Macro Programming**
    - `mprint`, `symbolgen`, `mlogic`
