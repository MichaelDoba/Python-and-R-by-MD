# Python-and-R-by-MD
## Weekly Payment System for Highridge Construction Company

This repository contains Python and R scripts to generate payment slips for workers based on salary and gender criteria.

## *📂 Repository Structure*

Highridge Construction Company-payment-system/
├── payment_system.py       # Python implementation
├── payment_system.R        # R implementation
└── README.md               # This documentation

## *🚀 Features*

- *Dynamic Workforce Generation*
  - Creates 400+ employee records with randomized:
    - Employee IDs
    - Salaries ($2,000-$35,000 range)
    - Gender distribution
      
- *Intelligent Classification*
  - Automatically assigns pay grades:
    - *A1*: Salary between $10,001-$19,999
    - *A5-F*: Salary between $7,501-$29,999 (Female only)
    - *Unclassified*: All other cases

- *Robust Error Handling*
  - Type checking
  - Missing data validation
  - Graceful error recovery

- *Formatted Output*
  - Standardized payment slip format
  - Proper number formatting (e.g., $15000)
  - Clear classification labeling

## *🛠 Installation*

## *Python Version*
bash
### Clone repository
git clone https://github.com/MichaelDoba/Python-and-R-by-MD/Highridge-Construction-Company-Payment-System.git

### No dependencies required
python payment_system.py


## *R Version*
bash
### Requires base R only
Rscript payment_system.R

## *🔍 Code Walkthrough*

## *Python Implementation*
python
### Configuration
TOTAL_WORKFORCE = 400  # Easily adjustable workforce size

### Generate random worker
workers = []
    for i in range(num_workers):
        ##Generate worker attributes
        name = f"Employee #-{i+1}"
        salary = random.randint(2000, 35000)
        gender = random.choice(['Male', 'Female'])

### Classification Logic
if 10000 < salary < 20000:
    pay_grade = "A1"
elif (7500 < salary < 30000) and (gender == "Female"):
    pay_grade = "A5-F"

## *R Implementation*
r
### Reproducible randomization
set.seed(123)  

### Data frame construction
 workers <- data.frame(
    name = paste0("Employee #-", 1:num_workers),
    salary = sample(2000:35000, num_workers, replace = TRUE),
    gender = sample(c("Male", "Female"), num_workers, replace = TRUE),
    level = character(num_workers),
    stringsAsFactors = FALSE
  )

## *⚠ Error Handling*

*Common Scenarios Addressed:*
1. Missing employee fields
2. Type mismatches
3. Unexpected gender entries
   
## *📝 Sample Output*
1. Payment slip for: Employee #-2, Gender: Male, Salary: $13603, Employee Level: A1
2. Payment slip for: Employee #-384, Gender: Female, Salary: $28562, Employee Level: A5-F
3. Payment slip for: Employee #-399, Gender: Male, Salary: $32435, Employee Level: unclassified
