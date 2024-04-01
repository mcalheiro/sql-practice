# sql-practice
My solutions for [SQL practice exercises](https://www.sql-practice.com/)

**[Easy]** Show first name, last name, and gender of patients whose gender is 'M'
```sql
SELECT first_name, last_name, gender
FROM patients
WHERE gender='M'
```

**[Easy]** Show first name and last name of patients who does not have allergies. (null)
```sql
SELECT first_name, last_name
FROM patients
WHERE allergies is null
```

**[Easy]** Show first name of patients that start with the letter 'C'
```sql
SELECT first_name
FROM patients
WHERE first_name like "C%"
```

**[Easy]** Show first name and last name of patients that weight within the range of 100 to 120 (inclusive)
```sql
SELECT first_name, last_name
FROM patients
WHERE weight >= 100 and weight <= 120
```

**[Easy]** Update the patients table for the allergies column. If the patient's allergies is null then replace it with 'NKA'
```sql
UPDATE patients
SET allergies = 'NKA'
WHERE allergies is NULL;
```

**[Easy]** Show first name and last name concatinated into one column to show their full name.
```sql
SELECT CONCAT(first_name, " ", last_name) as full_name
FROM patients
```

**[Easy]** Show first name, last name, and the **full** province name of each patient. Example: 'Ontario' instead of 'ON'
```sql
SELECT patients.first_name, patients.last_name, province_names.province_name
FROM patients
JOIN province_names
ON patients.province_id = province_names.province_id
```

**[Easy]** Show how many patients have a birth_date with 2010 as the birth year.
```sql
SELECT COUNT(birth_date)
FROM patients
WHERE YEAR(birth_date) is 2010
```

**[Easy]** Show the first_name, last_name, and height of the patient with the greatest height.
```sql
SELECT first_name, last_name, max(height) 
FROM patients
```

**[Easy]** Show all columns for patients who have one of the following patient_ids: 1,45,534,879,1000
```sql
SELECT *
FROM patients
WHERE patient_id in (1,45,534,879,1000)
```

**[Easy]** Show the total number of admissions
```sql
SELECT COUNT(patient_id)
FROM admissions
```

**[Easy]** Show all the columns from admissions where the patient was admitted and discharged on the same day.
```sql
SELECT *
FROM admissions
WHERE discharge_date = admission_date
```

**[Easy]** Show the patient id and the total number of admissions for patient_id 579.
```sql
SELECT patient_id, COUNT(patient_id)
FROM admissions
WHERE patient_id = 579
```

**[Easy]** Based on the cities that our patients live in, show unique cities that are in province_id 'NS'?
```sql
SELECT DISTINCT(city)
FROM patients
WHERE province_id IS "NS"
```

**[Easy]** Write a query to find the first_name, last name and birth date of patients who has height greater than 160 and weight greater than 70
```sql
SELECT first_name, last_name, birth_date
FROM patients
WHERE height > 160 and weight > 70
```

**[Easy]** Write a query to find list of patients first_name, last_name, and allergies where allergies are not null and are from the city of 'Hamilton'
```sql
SELECT first_name, last_name, allergies
FROM patients
WHERE allergies NOT null and city is "Hamilton"
```

