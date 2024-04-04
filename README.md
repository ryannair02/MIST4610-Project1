# MIST4610-Project1

**Team Name:**
**Group 4**

Team Members:

Marko, Matthew, [@Matthew-Marko](https://github.com/Matthew-Marko)

Muddala, Aniketh, [@anm36176](https://github.com/anm36176)

Nair, Ryan, [@ryannair02](https://github.com/ryannair02)

Pasupuleti, Chaitanya, [@cp12312112](https://github.com/cp12312112)

Valladares, Matthew, [@MatthewValladares](https://github.com/MatthewValladares)

**Problem Description**:

"Goal Achievers FC" has recently been facing challenges with managing player injuries, recovery timelines, and ensuring the availability of players for upcoming matches and training sessions. The club has experienced situations where the lack of real-time information on player recovery status has led to inadequate preparation for games and training sessions being less effective. Additionally, there's been difficulty in reporting and analyzing the frequency and types of injuries to implement preventative measures.

**Data Model**:
This model includes entities such as Coaches, Teams, Members, Injury Types, Training Facilities, Equipment, Suppliers, Uniform Orders, Injuries, Training Sessions, Matches, and Order Details. Below is a detailed description of each entity within your data model, its purpose, and how it relates to other entities.

**Entities and Their Descriptions**:

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

Purpose: Information on the club's equipment, including ID, date purchased, location, and facility ID.
Relationships: Equipment is tied to specific Training Facilities.

Suppliers

Purpose: Manages data about suppliers, including ID, address, phone number, order status, and order date.
Relationships: Suppliers are linked to Uniform Orders, indicating where the club's uniforms come from.

Uniform Orders

Purpose: Tracks orders for uniforms, including product ID, name, type, price, quantity, and supplier ID.
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

**Data Model**

![image](https://github.com/ryannair02/MIST4610-Project1/assets/150095773/3048c7d6-f865-4922-97a7-dde5bb20ec65)





**Data Dictionary**

![image](https://github.com/ryannair02/MIST4610-Project1/assets/165865808/958f6242-c381-4c2d-a8b0-985176a0a37d)
![image](https://github.com/ryannair02/MIST4610-Project1/assets/165865808/9da61f4d-5dca-4b89-bc76-4b1ed7c6d45a)
![image](https://github.com/ryannair02/MIST4610-Project1/assets/165865808/e9a11109-44b3-454e-b9e2-14f4a663b140)
![image](https://github.com/ryannair02/MIST4610-Project1/assets/165865808/061fc578-cee3-46f2-8a23-ecad4d4d50f2)
![image](https://github.com/ryannair02/MIST4610-Project1/assets/165865808/e4c6580b-71dc-418e-ae8c-69ec3d00effa)
![image](https://github.com/ryannair02/MIST4610-Project1/assets/165865808/1c12ff02-7a6c-4f3d-8d35-956be46c9f49)
![image](https://github.com/ryannair02/MIST4610-Project1/assets/165865808/33f9556e-dd9a-4234-a48c-245425653c96)
![image](https://github.com/ryannair02/MIST4610-Project1/assets/165865808/c9adbe75-1843-424b-ae8f-6511bd136da5)
![image](https://github.com/ryannair02/MIST4610-Project1/assets/165865808/0f5812f4-9398-498f-b854-d96f60088d9c)
![image](https://github.com/ryannair02/MIST4610-Project1/assets/165865808/204e38c7-b948-4866-a991-27ca68be09d1)
![image](https://github.com/ryannair02/MIST4610-Project1/assets/165865808/2c758146-23c2-4f7c-bfcd-69e378fffa31)
![image](https://github.com/ryannair02/MIST4610-Project1/assets/165865808/fa09dc08-c59a-425a-a493-e0682845f153)






Simple Queries: 

1) What are the coach's names and IDs who have more than 20 years of experience Order by years of experience descending.

   Justification: This query retrieves the names and IDs of coaches with over 20 years of experience, ordered by years of experience in descending order. It is valuable for the database since it identifies highly experienced coaches in the organization. Managers use this information to assign leadership roles, mentor younger coaches, and distribute resources effectively. Also, it helps planning by finding out which coaches are near retirement age. This supports informed decision-making and management of coaching overall.

   SQL code for Query 1:

   SELECT staffName, yearsOfExperience FROM Coaches WHERE yearsOfExperience > 20 ORDER BY yearsOfExperience DESC;

   Image for Query 1: <img width="205" alt="image" src="https://github.com/ryannair02/MIST4610-Project1/assets/120529297/7d611dc2-e2f6-4da8-a7c7-90c85a469f0a">

   2)List the equipment ID and date purchased for all equipment at Facility 4

   Justification: Managers responsible for Facility 4 need to have up to date inventory of equipment to ensure efficiency and proper maintenance. By listing the equipment ID and date of purchase for all equipment at Facility 4, managers can track the age of equipment, plan for maintenance schedules, and check the need for equipment replacements or upgrades. This will lead to smooth operations and utilization of equipment resources.

   SQL code for Query 2:

   SELECT equipmentID, datePurchased FROM Equipment WHERE facilityID = 4;

   Image for Query 2: <img width="220" alt="image" src="https://github.com/ryannair02/MIST4610-Project1/assets/120529297/e0839981-c9c8-40f4-8a53-cb6a56f312d1">

   3) List the team names who have won their match

      Justification: Managers are need to monitor team performance and identify successful teams within the organization to celebrate their achievements, distribute resources, and help replicate successful strategies across other teams in their training programs. By listing the team names that have won their matches, managers get insights into the performance of individual teams which helps them identify areas for improvement in other team. This information aids them in enhancing their teams overall and lead them to success.
      
      SQL code for Query 3:

      SELECT Teams_teamID, matchDate, opponent FROM Matches WHERE result = "win";
      
      Image for Query 3:<img width="203" alt="image" src="https://github.com/ryannair02/MIST4610-Project1/assets/120529297/3449530b-2351-4291-8149-77b12022b9e6">

      4) What is the supplier ID and phone number of orders that have been canceled?

         Justification: Managing supplier relationships and making sure teams get their orders on time are really important for managers. When they know which suppliers were involved in canceled orders, it helps them spot potential problems early. They can reach out to them quickly, sort things out, and try to avoid more cancellations later on. Having the supplier ID and contact info from canceled orders allows them to get in touch with them fast. 

      SQL code for Query 4:

       SELECT supplierID, phone FROM Suppliers Where orderStatus = 'Cancelled';

         Image for Query 4: <img width="195" alt="image" src="https://github.com/ryannair02/MIST4610-Project1/assets/120529297/aac59f2b-ab03-435b-91f9-9b25a4dbf14b">


**Complex Queries:** 

Query 5:
List out the members who have not put any Uniform or Equipment Orders and the sessions they have played in.
   
   Justification: Managers of the teams need to know which players have not put in an order for any Uniforms or Equipment. This is crucial for the safety of the members as they should not be playing in any of the sessions without the proper equipment. If the player has been in sessions without the proper saftey equipment and uniforms, they should be notified and taken out until they have what they need.

   Image for Query 5: 
   ![image](https://github.com/ryannair02/MIST4610-Project1/assets/163185043/dee03459-9da8-4d69-b2df-ea44f36f2573)


SQL code for Query 5:
  
   SELECT M.memberID, M.memberName, T.teamID, T.ageGroup, T.skillLevel, TS.sessionID, TS.date AS 'Session Date', TS.time AS 'Session Time', TS.location AS 'Session Location'
FROM Members M
JOIN Teams T ON M.teamID = T.teamID
JOIN `Training Sessions` TS ON T.teamID = TS.Teams_teamID
WHERE NOT EXISTS (SELECT *
FROM `Order Details` OD 
JOIN `Uniform Orders` UO ON OD.productID = UO.productID
WHERE OD.memberID = M.memberID) ORDER BY M.memberID;


Query 6:
List the top Supplier by Total Order Amount
   
   Justification: This information is crucial for evaluating supplier performance, optimizing inventory management, and making strategic procurement decisions, ensuring efficient and cost-effective supply chain operations.

SQL code for Query 6: 

SELECT Suppliers.supplierID, Suppliers.address, Suppliers.phone,
       SUM(`Uniform Orders`.price * `Uniform Orders`.quantity) AS TotalOrderAmount
FROM Suppliers
JOIN `Uniform Orders` ON Suppliers.supplierID = `Uniform Orders`.supplierID
GROUP BY Suppliers.supplierID, Suppliers.address, Suppliers.phone
ORDER BY TotalOrderAmount DESC;


Image for Query 6: <img width="411" alt="image" src="https://github.com/ryannair02/MIST4610-Project1/assets/120529297/cd549893-4e7e-4a38-9335-389cf7cf4b92">


Query 7:
Total Number of Injuries by Team
   
   Justification: Team-level injury statistics are important for managers to check the overall injuries within each team. Team managers and coaches can use this information to evaluate the effectiveness of their training programs, identify teams at higher risk of injuries, and appropriate resources for injury prevention measures accordingly.

Sql code for Query 7: 

SELECT `Teams`.`teamID`, COUNT(`Injuries`.`injuryID`) AS TotalInjuries
FROM `Teams`
JOIN `Members` ON `Teams`.`teamID` = `Members`.`teamID`
JOIN `Injuries` ON `Members`.`memberID` = `Injuries`.`Members_memberID`
GROUP BY `Teams`.`teamID`;

Image for Query 7: <img width="277" alt="image" src="https://github.com/ryannair02/MIST4610-Project1/assets/120529297/b2f1b98f-1cfd-4055-a97e-ebf00dba8efe">

Query 8:
Display in a procedure the players, age group, and teamID while calling a particular teamID.

Justification:
This query is helpful for the club to quickly access the list of players, their age group, and the teamID of a particular team. This query would assist a club admin when dealing with daily operations of the club regarding a particular team and their members.


Sql code for Query 8: 

CREATE PROCEDURE membersOfTeams(IN theTeamID INT)
  SELECT memberName, ageGroup, Teams.teamID
  FROM al_Group_21479_G4.Teams
  JOIN al_Group_21479_G4.Members ON Teams.teamID=Members.teamID
  WHERE Teams.teamID = theTeamID; 
   
   CALL membersOfTeams(4);

![image](https://github.com/ryannair02/MIST4610-Project1/assets/165865808/87647fca-9362-4b22-b61b-919d4530bd3f)


Query 9:
Identify teams with more than 2 members aged below 18.

Justification: It is crucial for managers to know which of the team's members are below 18 since that would make them minors. For minors in sports, there are several laws and regulations that must be followed or else the team and managers will get into much trouble. Through this, the managers will be able to spot if they have a lot of team members under 18. They can also give them proper training that is in compliance with the regulations and allocate funds towards this.

Sql Code for Query 9: 

SELECT Teams.teamID, COUNT(Members.memberID) AS TotalMembers
FROM Teams
JOIN Members ON Teams.teamID = Members.teamID
WHERE YEAR(CURDATE()) - YEAR(Members.memberDOB) < 18
GROUP BY Teams.teamID
HAVING TotalMembers > 2;

Image for Query 9: <img width="402" alt="image" src="https://github.com/ryannair02/MIST4610-Project1/assets/120529297/347f6d54-2877-406f-80bf-6a010e9bfb00">
 
 
Query 10: 
List all teams along with the count of members and the average age of members in each team.
  
   Justification: Understanding team composition and demographics is important for team management as well as for dividing resources the correct way. By listing all teams along with the count of members and the average age of members in each team, managers gain insights into team dynamics, diversity, and sometimes even skill gaps. This information will help the managers see team performance,  training needs, and allocation of resources  to support team development and productivity. Also, knowing the average age of team members allows managers to give proper communication and leadership strategies which fit the needs of different age groups in the teams, allowing for better training sessions.


Sql code:

SELECT Teams.teamID, COUNT(Members.memberID) AS TotalMembers, AVG(YEAR(CURDATE()) - YEAR(Members.memberDOB)) AS AvgAge
FROM Teams
JOIN Members ON Teams.teamID = Members.teamID
GROUP BY Teams.teamID;

Image for Query 10: <img width="253" alt="image" src="https://github.com/ryannair02/MIST4610-Project1/assets/120529297/9fa2ecf1-8169-451d-b5f0-45a217ba0f2f">

![image](https://github.com/ryannair02/MIST4610-Project1/assets/163185043/bca2d694-6a53-4520-acac-d7384586dce3)

