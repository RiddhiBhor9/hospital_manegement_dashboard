# hospital_manegement_dashboard
 1. Basic Analysis
-- Total patients
SELECT COUNT(*) FROM hospital_data;

-- Average age
SELECT AVG(age) FROM hospital_data;

-- Average cost
SELECT AVG(cost) FROM hospital_data;
 2. Group Analysis
-- Patients by gender
SELECT gender, COUNT(*) 
FROM hospital_data 
GROUP BY gender;

-- Patients by condition
SELECT condition, COUNT(*) 
FROM hospital_data 
GROUP BY condition 
ORDER BY COUNT(*) DESC;
 3. Cost Analysis
-- Max & Min cost
SELECT MAX(cost), MIN(cost) FROM hospital_data;

-- Average cost by condition
SELECT condition, AVG(cost) 
FROM hospital_data 
GROUP BY condition;
 4. Hospital Insights
-- Average stay by procedure
SELECT procedure, AVG(length_of_stay) 
FROM hospital_data 
GROUP BY procedure;

-- Readmission count
SELECT readmission, COUNT(*) 
FROM hospital_data 
GROUP BY readmission;
 5. Satisfaction Analysis
-- Average satisfaction
SELECT AVG(satisfaction) FROM hospital_data;

-- Satisfaction by outcome
SELECT outcome, AVG(satisfaction) 
FROM hospital_data 
GROUP BY outcome;
 6. Advanced Queries (for project)
-- Top 3 costly conditions
SELECT condition, AVG(cost) AS avg_cost
FROM hospital_data
GROUP BY condition
ORDER BY avg_cost DESC
LIMIT 3;

-- Patients with high cost (>20000)
SELECT * FROM hospital_data
WHERE cost > 20000;

-- Patients stayed more than 7 days
SELECT * FROM hospital_data
WHERE length_of_stay > 7;
 7. Dashboard Type Query
-- Combined summary
SELECT 
    COUNT(*) AS total_patients,
    AVG(age) AS avg_age,
    AVG(cost) AS avg_cost,
    AVG(satisfaction) AS avg_satisfaction
FROM hospital_data;
