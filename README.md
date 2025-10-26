# MIST 4610 Group Project: Group 7

## Team Name and Members:
Team Name: Group 7

Team Members:
1. Audrey Staples - https://github.com/audreystaples/mist4610groupproject 
2. Angela Ren - https://github.com/angelaaa456/mist4610groupproject 
3. Sammy Effron - https://github.com/Seffron/4610Group7
4. Tanner Sutherland - https://github.com/tannersutherland/mist4610groupproject 
5. Tyler Schildkraut - https://github.com/tylerschildkraut/MIST-4610-Project-Group-7

## Scenario Description:
We wanted to construct a data model that organizes key information used to navigate the NCAA college football landscape. The ultimate goal for our model is to represent the various relationships that exist among Coaches, Teams, Players, Rosters, Games, etc. in a way that mirrors how real NCAA programs operate. Although our data is hypothetical, it represents pertinent information that would meet managerial requirements within the NCAA ecosystem. From surveying game statistics to determining player status on a roster, our database provides insights that would prove highly useful to NCAA stakeholders. Ultimately, we aimed to create a database that would effectively aid managerial decision making within essential business units such as logistics management, decision-making, and reporting within an ever evolving industry.

## Data Model:
<img width="667" height="765" alt="MIST 4610 GP Data Model" src="https://github.com/user-attachments/assets/cfa0e031-3c1b-4d53-a410-627d795970bf" />

**Explanation**: Our database is based on the NCAA with hypothetical data included for ease of data insertion. For instance, instead of the University of Georgia the record is the Athens Bulldogs.

Beginning with the Teams entity, we made teamID our identifier and included attributes such as teamName and conference. This entity relates to our Coaches entity with a one-to-many relationship because teams have many coaches, but those coaches are linked to only one team. Our Coaches entity is identified by the primary key coachID and contains attributes such as name, role which describes their specific coaching position (Head Coach, Offensive Coordinator, etc.), yearsOfExperience describing the amount of years of coaching experience they have, as well as a foreign key being teamID. Rosters represent the associative entity connecting the many-to-many relationship between Teams and Players as players can be on many teams and teams are composed of many players. Rosters are identified by rosterID, and they have attributes such as a foreign keys playerID and teamID. Additionally, Rosters display the startDate of a player’s commitment to a team as well as the endDate which could be null if the player is still playing on that team playing. Rosters also display the player’s position on that specific team as well as their jersey number on that specific team. The Players entity is identified by a unique playerID which is the primary key of that entity. In addition to that, the Players entity has attributes such as name, the player’s yearInSchool, their height in inches, their weight in pounds, and the status of their scholarship, if applicable. Additionally, the Players entity has a one-to-many relationship with the entity named Injuries as players can have many injuries but a specific instance of an injury can only occur once in one player. Injuries have the primary key injuryID along with attributes such as injuryName, lengthOfRecovery, surgery name if needed, as well as the foreign key playerID which specifies the one-to-many relationship.

Moving on to another key entity, we have Games. Games are identified by their primary key which is called gameID. Our Teams table has two one-to-many relationships with the Games entity meaning that one instance of a team (the home team) has many games but those games only have one home team. Additionally, another instance of a team (the away team) also has many Games but those specific games are only related to one away team. For that reason, our Games entity contains two foreign keys from the Teams table, one being homeTeamID and the other being awayTeamID. Another foreign key in the Games table is the stadiumID. The last attribute in the Games table is the date attribute which specifies the date the game occurred on. Our Stadiums table is connected to the Games entity by a one-to-many relationship. Stadiums house many games but those games can only be played at one stadium at a time. Stadiums are also identified by attributes such as stadiumName, city, and capacity. Stadiums also have a one-to-many relationship with Seats because a stadium has many seats but a seat can only be in one stadium. Seats have the primary key seatID as well as attributes like section, row, seatNumber, seatType, and the foreign key stadiumID. Seats also have a one-to-many relationship with Tickets as a seat can be sold by many tickets but tickets only are attached to one seat. Tickets are identified by ticketID, and have attributes such as price, ticketHolderName, the foreign key gameID, and the foreign key seatID. This then brings about the relationship between Games and Tickets being one-to-many as games have many tickets but a specific ticket is only attached to one game. The last entity that needs describing is our Statistics entity. Statistics has a many-to-one relationship with Players as Players have many statistics but a specific statistic is only connected to one player. Another relationship that exists with Statistics is a many-to-one relationship with Games. Statistics are present in many games, but a game only has one instance of a specific player statistic. Statistics are identified by a statID, a foreign key of playerID, yards if applicable, touchdowns if applicable, tackles if applicable, interceptions if applicable, receptions if applicable, fieldGoals if applicable, as well as the foreign key gameID.

## Data Dictionary:

<img width="605" height="154" alt="Stadiums Data Dictionary" src="https://github.com/user-attachments/assets/30a267e8-f861-4d26-9fc5-8a94902d76b9" />
<img width="612" height="198" alt="Coaches Data Dictionary" src="https://github.com/user-attachments/assets/128a62d5-4f8b-49c4-941d-cb6416d922c2" />
<img width="606" height="238" alt="Seats Data Dictionary" src="https://github.com/user-attachments/assets/49cab26c-edca-4dd8-a365-047b713baa16" />
<img width="612" height="208" alt="Games Data Dictionary" src="https://github.com/user-attachments/assets/3ad52026-13c8-4566-b4b8-dafe6fcc5510" />
<img width="599" height="237" alt="Tickets Data Dictionary" src="https://github.com/user-attachments/assets/ee7e317a-40ef-463d-9eb2-a2fb19e555fa" />
<img width="639" height="422" alt="Injuries Data Dictionary" src="https://github.com/user-attachments/assets/ec169779-2899-428b-a8fe-f9fc9972e979" />
<img width="643" height="637" alt="Statistics Data Dictionary" src="https://github.com/user-attachments/assets/574ac614-2509-4389-b3f8-c0e8cbdf6b1b" />
<img width="633" height="387" alt="Players Data Dictionary" src="https://github.com/user-attachments/assets/8b85cd4f-2db7-4573-a885-b226e02c963f" />
<img width="640" height="532" alt="Rosters Data Dictionary" src="https://github.com/user-attachments/assets/c395acd5-a1de-4531-9f80-731059d43eb9" />
<img width="638" height="265" alt="Teams Data Dictionary" src="https://github.com/user-attachments/assets/e6e5e1f2-ce77-4d8c-9743-84999827a4a4" />

## Queries:

<img width="643" height="309" alt="Screenshot 2025-10-26 at 11 43 06 AM" src="https://github.com/user-attachments/assets/24f7d94b-3f4b-442f-945f-46e01d863ae4" />

1. Query 1 shows every team and counts how many players are currently listed on their roster. It joins the Teams and Rosters tables using the teamID to associate players with their teams, then groups the results by each team name.

<img width="548" height="172" alt="TP1" src="https://github.com/user-attachments/assets/e1c07566-d9a5-4889-9ab6-d3b1622179c6" />
<img width="416" height="608" alt="TP1 Results" src="https://github.com/user-attachments/assets/b5c1c943-768c-47b5-a24a-e89206aa716f" />

Text Results:
Execute:
> SELECT teamName, COUNT(playerID) AS PlayerCount
FROM Teams
JOIN Rosters ON Teams.teamID = Rosters.teamID
GROUP BY teamName

+ ------------- + ---------------- +
| teamName      | PlayerCount      |
+ ------------- + ---------------- +
| Athens Bulldogs | 3                |
| Madison Badgers | 3                |
| Columbus Buckeyes | 2                |
| Ann Arbor Wolverines | 2                |
| State College Nittany Lions | 3                |
| East Lansing Spartans | 2                |
| Minneapolis Gophers | 2                |
| Lincoln Huskers | 2                |
| Iowa City Hawkeyes | 2                |
| Champaign Illini | 2                |
| Evanston Wildcats | 3                |
| Piscataway Scarlet Knights | 2                |
| College Park Terrapins | 2                |
| Seattle Huskies | 2                |
| Eugene Ducks  | 2                |
| Los Angeles Bruins | 2                |
| Los Angeles Trojans | 2                |
| Bloomington Hoosiers | 2                |
| West Lafayette Boilermakers | 2                |
| Austin Longhorns | 2                |
| Norman Sooners | 2                |
| Tuscaloosa Crimson Tide | 2                |
| Baton Rouge Tigers | 2                |
+ ------------- + ---------------- +
23 rows

Managerial Justification:
Roster size directly affects scholarship budgeting, recruiting needs, and practice planning. Athletic departments can use this information to verify roster compliance with NCAA limits (e.g., 85 scholarship players in Division I football) and identify whether certain teams are under- or over-staffed. It also provides insights for coaching staff to balance positional depth across the roster.

2. Query 2 calculates the total number of offensive yards gained by each player across all games using the Statistics table. The query groups by player name and sums their yards column, returning players in descending order of total yardage.

<img width="607" height="152" alt="TP2" src="https://github.com/user-attachments/assets/0a5da935-bc5c-4c98-ab3d-4c15f22b0979" />
<img width="309" height="642" alt="TP2 Results" src="https://github.com/user-attachments/assets/6f3d978c-df71-419c-92db-8ef004c18d40" />

Text Results:
Execute:
> SELECT name AS PlayerName, SUM(yards) AS TotalYards
FROM Players
JOIN Statistics ON Players.playerID = Statistics.playerID
GROUP BY name

+ --------------- + --------------- +
| PlayerName      | TotalYards      |
+ --------------- + --------------- +
| Tyler Moore     | 526             |
| Connor Davis    | 303             |
| Noah Lewis      | 153             |
| Zach Moore      | 322             |
| Connor White    | 480             |
| Aaron Jones     | 65              |
| Connor Martinez | 260             |
| David Harris    | 147             |
| James Anderson  | 157             |
| John Miller     | 289             |
| Ethan Wilson    | 461             |
| Luke Moore      | 521             |
| Alex Smith      | 449             |
| Logan Martinez  | 331             |
| Michael Taylor  | 447             |
| Justin Davis    | 168             |
| Jordan Moore    | 324             |
| Ryan White      | 195             |
| Josh Johnson    | 579             |
| Nick Lewis      | 251             |
| Matt Jones      | 350             |
| Ethan Smith     | 148             |
| Michael Walker  | 67              |
| Zach Harris     | 190             |
| John Johnson    | 282             |
| Michael Thomas  | 159             |
| Michael Harris  | 20              |
| Aaron Thomas    | 40              |
| Dylan Walker    | 77              |
| James Clark     | 112             |
+ --------------- + --------------- +
30 rows

Managerial Justification:
Tracking cumulative yardage helps offensive coordinators evaluate player impact and consistency. This data is key for determining award nominations, highlighting top performers in media relations, and identifying players who may deserve more playing time or position adjustments based on productivity.

3. Query 3 identifies all players who have not yet recorded any game statistics by checking which player IDs are not present in the Statistics table.

<img width="615" height="136" alt="TP3" src="https://github.com/user-attachments/assets/6e87310c-3a16-4491-8663-77fb208f964a" />
<img width="273" height="569" alt="TP3 Results" src="https://github.com/user-attachments/assets/a8b0495a-cf2b-431a-b663-570625549c3e" />

Text Results:
Execute:
> SELECT name
FROM Players
WHERE playerID NOT IN (SELECT playerID FROM Statistics)

+ --------- +
| name      |
+ --------- +
| Noah Johnson |
| Josh Thomas |
| Jordan Garcia |
| Nick Thomas |
| Chris Harris |
| Noah Smith |
| Josh Smith |
| Michael Moore |
| Alex Walker |
| Luke Brown |
| David Clark |
| Tyler Garcia |
| James Thompson |
| Kyle Davis |
| Kyle Martinez |
| Zach Jones |
| Logan Brown |
| Ryan Jones |
| Zach Clark |
| Zach Garcia |
+ --------- +
20 rows

Managerial Justification:
This helps coaching staff and analysts find players who have not appeared in any games and make decisions about those players accordingly. Managers can use this information to determine which players may need more opportunities to play or to address what to do with those players in the future.

4. Query 4 displays all players who have sustained more than one recorded injury. It joins Players and Injuries using playerID, groups the results by player, and filters using a HAVING clause.

<img width="572" height="189" alt="TP4" src="https://github.com/user-attachments/assets/a96ca09f-9293-4fc4-9ae8-2adf32559942" />
<img width="295" height="457" alt="TP4 Res" src="https://github.com/user-attachments/assets/3d4cbbdf-6d99-41c4-8c84-8f3558bde037" />

Text Results:
Execute:
> SELECT name, COUNT(injuryID) AS TotalInjuries
FROM Players
JOIN Injuries ON Players.playerID = Injuries.playerID
GROUP BY name
HAVING COUNT(injuryID) > 1

+ --------- + ------------------ +
| name      | TotalInjuries      |
+ --------- + ------------------ +
| Tyler Moore | 2                  |
| Jordan Moore | 2                  |
| Ethan Smith | 3                  |
| Michael Taylor | 3                  |
| Alex Walker | 3                  |
| Zach Moore | 2                  |
| James Anderson | 3                  |
| Ethan Wilson | 2                  |
| Kyle Martinez | 2                  |
| Logan Brown | 4                  |
| James Clark | 2                  |
+ --------- + ------------------ +
11 rows

Managerial Justification:
Identifying players with frequent injuries allows medical staff to implement personalized recovery or training programs. Coaches can use this information to manage playing time and avoid re-injury, which reduces long-term risk and protects the team’s investment in scholarship athletes.

5. Query 5 finds the average weight of players for each position across all rosters. It joins Rosters and Players and groups the results by position.

<img width="596" height="143" alt="TP 5" src="https://github.com/user-attachments/assets/d5f9977d-5514-4254-bab3-2a5e212aadac" />
<img width="268" height="426" alt="TP5 Res" src="https://github.com/user-attachments/assets/20dd4950-aab1-4ada-a972-c301b8eb973e" />

Text Results: 
Execute:
> SELECT position, ROUND(AVG(`weight (in lbs)`), 1) AS AvgWeight
FROM Rosters
JOIN Players ON Rosters.playerID = Players.playerID
GROUP BY position

+ ------------- + -------------- +
| position      | AvgWeight      |
+ ------------- + -------------- +
| QB            | 243.7          |
| RB            | 222.1          |
| WR            | 223.2          |
| LB            | 198.3          |
| TE            | 238.7          |
| CB            | 255.0          |
| DL            | 238.8          |
| S             | 245.0          |
| OL            | 206.0          |
+ ------------- + -------------- +
9 rows

Managerial Justification:
Weight and conditioning benchmarks are crucial for maintaining competitiveness. This data helps strength and conditioning coaches monitor whether players at each position (e.g., linemen, receivers, linebackers) meet desired physical standards and make training adjustments if a position group is under or over target weight ranges. AI was utilized here to locate the backticks function which allowed for the system to not confuse the parentheses in the column title with SQL script parentheses.

6. Query 6 shows the number of total games each team has participated in—both home and away. It joins Teams and Games and counts how many times a team appears as either the home or away team.

<img width="614" height="120" alt="TP6" src="https://github.com/user-attachments/assets/f434a75f-2863-43db-a239-240f5d048423" />
<img width="392" height="659" alt="TP6 Results" src="https://github.com/user-attachments/assets/017b1731-c314-4ca4-9b64-8ea06f1b849e" />

Text Results:
Execute:
> SELECT teamName, COUNT(gameID) AS TotalGames
FROM Teams
JOIN Games ON Teams.teamID = Games.homeTeamID OR Teams.teamID = Games.awayTeamID
GROUP BY teamName

+ ------------- + --------------- +
| teamName      | TotalGames      |
+ ------------- + --------------- +
| Athens Bulldogs | 2               |
| Madison Badgers | 2               |
| Columbus Buckeyes | 2               |
| Ann Arbor Wolverines | 2               |
| State College Nittany Lions | 2               |
| East Lansing Spartans | 2               |
| Minneapolis Gophers | 2               |
| Lincoln Huskers | 2               |
| Iowa City Hawkeyes | 2               |
| Champaign Illini | 2               |
| Evanston Wildcats | 2               |
| Piscataway Scarlet Knights | 2               |
| College Park Terrapins | 2               |
| Seattle Huskies | 2               |
| Eugene Ducks  | 2               |
| Los Angeles Bruins | 2               |
| Los Angeles Trojans | 2               |
| Bloomington Hoosiers | 2               |
| West Lafayette Boilermakers | 2               |
| Austin Longhorns | 2               |
| Norman Sooners | 2               |
| Tuscaloosa Crimson Tide | 2               |
| Baton Rouge Tigers | 2               |
| Athens Classic Dawgs | 2               |
| Gainesville Gators | 2               |
| Knoxville Volunteers | 2               |
| Oxford Rebels | 2               |
| Starkville Bulldogs | 2               |
| Fayetteville Razorbacks | 2               |
| Columbia Gamecocks | 2               |
| College Station Aggies | 2               |
| Lexington Wildcats | 2               |
| Nashville Commodores | 2               |
| Tallahassee Seminoles | 2               |
| Clemson Tigers | 2               |
| Chapel Hill Tar Heels | 2               |
| Durham Blue Devils | 2               |
| Raleigh Wolfpack | 2               |
| Blacksburg Hokies | 2               |
| Charlottesville Cavaliers | 2               |
| Coral Gables Hurricanes | 2               |
| Winston-Salem Demon Deacons | 2               |
| Syracuse Orange | 2               |
| Pittsburgh Panthers | 2               |
| Berkeley Golden Bears | 2               |
| Boulder Buffaloes | 2               |
| Salt Lake City Utes | 2               |
| Tempe Sun Devils | 2               |
| Tucson Wildcats | 2               |
| Provo Cougars | 2               |
+ ------------- + --------------- +
50 rows

Managerial Justification:
Tracking total games played helps administrators measure team activity levels across the season and can highlight scheduling imbalances. Operations teams can use this data to evaluate travel frequency, ensure scheduling fairness, and make logistical improvements for future seasons.

7. Query 7 lists all players who currently receive full athletic scholarships, ordered alphabetically by name.

<img width="441" height="161" alt="TP7" src="https://github.com/user-attachments/assets/c97fd771-dfe0-4c39-ade1-16d49fd443bf" />
<img width="466" height="614" alt="TP7 Results" src="https://github.com/user-attachments/assets/8610dbb4-29a7-47f9-bb87-41c5ee239f0c" />

Text Results: 
Execute:
> SELECT name, yearInSchool, scholarship
FROM Players
WHERE scholarship = "Full Scholarship"
ORDER BY name

+ --------- + ----------------- + ---------------- +
| name      | yearInSchool      | scholarship      |
+ --------- + ----------------- + ---------------- +
| Aaron Jones | 5th Year          | Full Scholarship |
| Alex Smith | 4th year          | Full Scholarship |
| Connor Davis | 4th Year          | Full Scholarship |
| Connor White | 5th Year          | Full Scholarship |
| David Clark | 4th Year          | Full Scholarship |
| Dylan Walker | 2nd Year          | Full Scholarship |
| James Anderson | 3rd Year          | Full Scholarship |
| Josh Johnson | 5th Year          | Full Scholarship |
| Luke Brown | 3rd Year          | Full Scholarship |
| Michael Moore | 4th Year          | Full Scholarship |
| Nick Lewis | 1st Year          | Full Scholarship |
| Noah Johnson | 2nd Year          | Full Scholarship |
| Noah Smith | 4th Year          | Full Scholarship |
| Tyler Garcia | 2nd Year          | Full Scholarship |
| Tyler Moore | 3rd Year          | Full Scholarship |
| Zach Clark | 2nd Year          | Full Scholarship |
| Zach Garcia | 1st Year          | Full Scholarship |
+ --------- + ----------------- + ---------------- +
17 rows

Managerial Justification:
Scholarship allocation is one of the largest financial responsibilities for athletic programs. This query helps compliance officers ensure that scholarship funds are properly assigned and enables administrators to monitor financial obligations and renewal cycles.

8. Query 8 displays the injuries in the database with the longest reported recovery times, ordered from longest to shortest.

<img width="543" height="144" alt="TP8" src="https://github.com/user-attachments/assets/e9d03a38-77ab-493d-ba8f-33d282e600cc" />
<img width="395" height="617" alt="TP8 Results" src="https://github.com/user-attachments/assets/26b459e8-9b81-430a-9c99-6f0cd1ecf3a4" />

Text Results:
Execute:
> SELECT injuryName, lengthOfRecovery
FROM Injuries
ORDER BY CAST(lengthOfRecovery AS UNSIGNED) DESC

+ --------------- + --------------------- +
| injuryName      | lengthOfRecovery      |
+ --------------- + --------------------- +
| Turf Toe        | 12 weeks              |
| Groin Pull      | 12 weeks              |
| Wrist Fracture  | 12 weeks              |
| Fractured Rib   | 12 weeks              |
| Shoulder Dislocation | 12 weeks              |
| Neck Strain     | 12 weeks              |
| Torn Achilles   | 10 weeks              |
| Shoulder Dislocation | 10 weeks              |
| MCL Sprain      | 8 weeks               |
| Wrist Fracture  | 8 weeks               |
| Elbow Dislocation | 8 weeks               |
| Elbow Dislocation | 8 weeks               |
| Torn Rotator Cuff | 8 weeks               |
| Groin Pull      | 8 weeks               |
| Hip Flexor Strain | 6 weeks               |
| Elbow Dislocation | 6 weeks               |
| Hip Flexor Strain | 6 weeks               |
| Foot Fracture   | 6 weeks               |
| Neck Strain     | 6 weeks               |
| Elbow Dislocation | 6 weeks               |
| Shoulder Dislocation | 6 weeks               |
| Broken Collarbone | 6 weeks               |
| Turf Toe        | 4 weeks               |
| Back Spasms     | 4 weeks               |
| Groin Pull      | 4 weeks               |
| Elbow Dislocation | 4 weeks               |
| Neck Strain     | 4 weeks               |
| Torn Achilles   | 4 weeks               |
| Fractured Rib   | 4 weeks               |
| Wrist Fracture  | 2 weeks               |
| Hand Fracture   | 2 weeks               |
| Neck Strain     | 2 weeks               |
| ACL Tear        | 2 weeks               |
| Bruised Lung    | 2 weeks               |
| Back Spasms     | 2 weeks               |
| MCL Sprain      | 2 weeks               |
| Neck Strain     | 2 weeks               |
| Torn Achilles   | 2 weeks               |
| Elbow Dislocation | 2 weeks               |
| Torn Rotator Cuff | 2 weeks               |
| Elbow Dislocation | 2 weeks               |
| Neck Strain     | Season-ending         |
| Ankle Sprain    | Season-ending         |
| Neck Strain     | Season-ending         |
| Bruised Lung    | Season-ending         |
| Broken Collarbone | Season-ending         |
| Back Spasms     | Season-ending         |
| Broken Arm      | Season-ending         |
| Hip Flexor Strain | Season-ending         |
| Bruised Lung    | Season-ending         |
+ --------------- + --------------------- +
50 rows

Managerial Justification:
Provides insight into which types of injuries are most severe and time-consuming to heal. This allows sports medicine staff to plan future prevention programs, identify potential insurance or cost implications, and communicate expected recovery timelines to coaches and media. Although we had not yet learned this feature, we utilized AI to accomplish this query as the VARCHAR() data format is not compatible with the ORDER BY DESC or ASC capabilities. Utilizing CAST and UNSIGNED, our string data values were converted to numbers effectively.

9. Query 9 calculates the average price of tickets sold for each game by joining the Games and Tickets tables and grouping results by gameID.

<img width="584" height="97" alt="TP9" src="https://github.com/user-attachments/assets/6f2cba42-f5c1-4b78-9332-ebae4a184b98" />
<img width="261" height="609" alt="TP9 Results" src="https://github.com/user-attachments/assets/c47904f9-ab9d-4f67-9003-727dcd02a261" />

Text Results:
Execute:
> SELECT Games.gameID, ROUND(AVG(CAST(REPLACE(price, '$', '') AS DECIMAL (10,2))), 2) AS AvgPrice
FROM Games
JOIN Tickets ON Games.gameID = Tickets.gameID
GROUP BY Games.gameID

+ ----------- + ------------- +
| gameID      | AvgPrice      |
+ ----------- + ------------- +
| 24          | 83.00         |
| 8           | 217.50        |
| 2           | 151.00        |
| 34          | 183.00        |
| 39          | 180.00        |
| 21          | 90.67         |
| 1           | 162.00        |
| 11          | 39.00         |
| 49          | 115.00        |
| 31          | 64.00         |
| 23          | 247.00        |
| 40          | 191.00        |
| 28          | 205.50        |
| 36          | 61.00         |
| 33          | 207.00        |
| 12          | 143.00        |
| 4           | 237.00        |
| 6           | 161.00        |
| 19          | 143.00        |
| 20          | 163.00        |
| 7           | 183.50        |
| 43          | 101.50        |
| 30          | 71.00         |
| 16          | 132.50        |
| 13          | 129.50        |
| 41          | 187.00        |
| 5           | 94.00         |
| 44          | 26.00         |
| 29          | 92.00         |
| 32          | 104.00        |
| 3           | 102.00        |
| 10          | 124.00        |
| 27          | 62.00         |
+ ----------- + ------------- +
33 rows

Managerial Justification:
Understanding average ticket prices helps the marketing and sales department assess revenue potential per game. It also reveals which matchups draw higher-paying audiences, allowing pricing strategies to be adjusted for rivalry or high-demand games to maximize profits. Similarly as before, we utilized the CAST function so that we could convert the original VARCHAR value of the price attribute in the Tickets entity to DECIMAL data formats so that we would be able to perform aggregations on the values.

10. Query 10 lists the five players with the highest total touchdowns recorded across all games.

<img width="563" height="178" alt="Screenshot 2025-10-26 at 12 06 52 PM" src="https://github.com/user-attachments/assets/9a23f071-dca5-4210-856e-e9d4dd6add3f" />
<img width="349" height="319" alt="Screenshot 2025-10-26 at 12 07 08 PM" src="https://github.com/user-attachments/assets/7dfe02e3-8de9-4556-9f65-4ec8cbab5e99" />

Text Results:
Execute:
> SELECT name, SUM(touchdowns) AS TotalTouchdowns
FROM Players JOIN Statistics ON Players.playerID = Statistics.playerID
GROUP BY name
ORDER BY TotalTouchdowns DESC LIMIT 5

+ --------- + -------------------- +
| name      | TotalTouchdowns      |
+ --------- + -------------------- +
| Alex Smith | 15                   |
| Logan Martinez | 9                    |
| Luke Moore | 8                    |
| Dylan Walker | 7                    |
| Zach Harris | 7                    |
+ --------- + -------------------- +
5 rows

Managerial Justification:
This helps highlight standout offensive players for performance evaluations, awards, and media recognition. Teams can also use this information for recruiting promotions and identifying which athletes consistently contribute to scoring. The LIMIT 5 function, which we learned through use of AI, allowed us to locate the top 5 players worth considering.














