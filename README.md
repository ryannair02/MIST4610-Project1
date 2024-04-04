# MIST4610-Project1

Team Name:
Group 4

Team Members:

Marko, Matthew, mm90925

Muddala, Aniketh, anm36176

Nair, Ryan, an94397

Pasupuleti, Chaitanya, cvp78617

Valladares, Matthew, mjv46711

Problem Description:

"Goal Achievers FC" has recently been facing challenges with managing player injuries, recovery timelines, and ensuring the availability of players for upcoming matches and training sessions. The club has experienced situations where the lack of real-time information on player recovery status has led to inadequate preparation for games and training sessions being less effective. Additionally, there's been difficulty in reporting and analyzing the frequency and types of injuries to implement preventative measures.

**Chat GPT Write-Up**
Business Overview
Core Activities: The club focuses on training sessions for different age groups, organizing friendly matches and participating in competitive leagues. We also host soccer camps and clinics.
Members: Our members range from young children starting out in soccer to teenagers and young adults playing at competitive levels. We categorize members by age groups and skill levels.
Staff: Our team includes coaches, assistant coaches, fitness trainers, a physiotherapist, and administrative personnel such as a club manager, membership coordinator, and financial officer.
Facilities: The club owns a soccer field, training equipment, a clubhouse with locker rooms, and an office for administrative tasks.
Entities, Attributes, and Relationships
To effectively manage our operations and maintain detailed records, the database should encapsulate the following entities, attributes, and relationships:



**Link to access google doc with data dictionary and queries and data model**
https://docs.google.com/document/d/1J_VV84QetjjWXdCdk3BOpeR5jTU0nQzsBZr7BnXAI-s/edit?usp=sharing


Queries: 

1) What are the coach's names and IDs who have more than 20 years of experience Order by years of experience descending.
   Justification: This query retrieves the names and IDs of coaches with over 20 years of experience, ordered by years of experience in descending order. It is valuable for the database as it identifies highly experienced coaches within the organization. Managers can use this information to assign leadership roles, mentor younger coaches, and allocate coaching resources effectively. Additionally, it aids in succession planning by identifying coaches nearing retirement age. Ultimately, this query supports informed decision-making and strategic management of coaching talent within the sports organization.

   SQL code for Query 1: SELECT staffName, yearsOfExperience FROM Coaches WHERE yearsOfExperience > 20 ORDER BY yearsOfExperience DESC;

   Image for Query 1: <img width="205" alt="image" src="https://github.com/ryannair02/MIST4610-Project1/assets/120529297/7d611dc2-e2f6-4da8-a7c7-90c85a469f0a">

   2)List the equipment ID and date purchased for all equipment at Facility 4
   Justification: Managers responsible for Facility 4 need to maintain an updated inventory of equipment to ensure operational efficiency and timely maintenance. By listing the equipment ID and date of purchase for all equipment at Facility 4, managers can accurately track the age of equipment, plan for maintenance schedules, and assess the need for equipment replacements or upgrades. This information enables effective asset management, cost control, and resource allocation within Facility 4, contributing to smooth operations and optimal utilization of equipment resources.

   SQL code for Query 2: SELECT equipmentID, datePurchased FROM Equipment WHERE facilityID = 4;

   Image for Query 2: <img width="220" alt="image" src="https://github.com/ryannair02/MIST4610-Project1/assets/120529297/e0839981-c9c8-40f4-8a53-cb6a56f312d1">

   3) List the team names who have won their match
      Justification: Managers are keen on monitoring team performance and identifying successful teams within the organization to celebrate achievements, allocate resources effectively, and potentially replicate successful strategies across other teams. By listing the team names that have won their matches, managers gain valuable insights into the performance of individual teams, allowing them to recognize and reward success, identify areas for improvement, and allocate resources strategically. This information aids in fostering a culture of excellence, enhancing team morale, and driving overall organizational success.
      SQL code for Query 3:SELECT Teams_teamID, matchDate, opponent FROM Matches WHERE result = "win";
      
      Image for Query 3:<img width="203" alt="image" src="https://github.com/ryannair02/MIST4610-Project1/assets/120529297/3449530b-2351-4291-8149-77b12022b9e6">
