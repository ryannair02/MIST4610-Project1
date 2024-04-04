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

Data Model:
This model includes entities such as Coaches, Teams, Members, Injury Types, Training Facilities, Equipment, Suppliers, Uniform Orders, Injuries, Training Sessions, Matches, and Order Details. Below is a detailed description of each entity within your data model, its purpose, and how it relates to other entities.

Entities and Their Descriptions:

Coaches

Purpose: Stores information about coaches, including their ID, name, contact information, years of experience, and a link to medical staff (though this appears to be a misinterpretation, as medical staff are typically not coaches).
Relationships: Coaches are linked to Teams indicating which coach is responsible for which team.

Teams

Purpose: Captures details about different teams within the club, including their ID, age group, skill level, and the coach assigned to each team.
Relationships: Teams have a relationship with Coaches and Members (players), and are involved in Matches and Training Sessions.
Members

Purpose: Contains member information, including ID, name, date of birth, contact info, emergency contact, and the team they are affiliated with.
Relationships: Members are linked to Teams and are subject to Injuries.

Injury Type

Purpose: Lists types of injuries that can occur, including an ID, injury type, and a description.
Relationships: This serves as a reference for the Injuries table to specify what type of injury occurred.

Training Facilities

Purpose: Details about the club's facilities, including an ID, name, type, and location.
Relationships: Facilities are linked to Equipment, Training Sessions, and Matches to indicate where these activities or items are located.
Equipment

Purpose: Information on the club's equipment, including ID, date purchased, location, and the facility ID.
Relationships: Equipment is tied to specific Training Facilities.

Suppliers

Purpose: Manages data about suppliers, including ID, address, phone number, order status, and order date.
Relationships: Suppliers are linked to Uniform Orders, indicating where the club's uniforms come from.

Uniform Orders

Purpose: Tracks orders for uniforms, including product ID, name, type, price, quantity, and the supplier ID.
Relationships: This table is connected to Suppliers and indirectly affects Members through distribution.

Injuries

Purpose: Records details of injuries sustained by members, including the injury ID, member ID, type of injury, time of injury, and location.
Relationships: Injuries are linked to Members and the Injury Type, providing a detailed record of what injuries occur and to whom.

Training Sessions

Purpose: Schedules training sessions, including details about the facility used, the team participating, session ID, date, time, and location.
Relationships: Training Sessions are connected to Teams and Training Facilities, organizing where and when training occurs.
Matches

Purpose: Manages match information, including the facility where the match is held, the team ID, match ID, date, location, opponent, and result.
Relationships: Matches are linked to Teams and Training Facilities, documenting the outcomes and settings of competitive games.

Order Details

Purpose: Captures details of orders placed by members, including order ID, price, purchase date, member ID, and product ID.
Relationships: This table connects Members to Uniform Orders, tracking transactions within the club.



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
