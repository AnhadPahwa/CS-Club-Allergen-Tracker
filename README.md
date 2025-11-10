# CS-Club-Allergen-Tracker
ACS Computer Science Club

**Architecture:-**

_Frontend (User Side)-_

Platform: Web app (React / Vue) or Mobile app (React Native / Flutter)


Features:

	- Input form for reports
	
	- Map view to explore neighborhood conditions
	
	- Charts/trends (basic graphs of allergens, reports over time)
	
	- Gamification UI (badges, leaderboard)


			
_Backend (API Layer)-_

Platform: Node.js (Express) or Python (Flask/Django)


Responsibilities:

	- Handle new report submissions (POST /report)
	
	- Fetch reports for a given location/time (GET /reports?location=...)
	
	- Aggregate data (counts, trends) for graphs
	
	- User management (optional, for gamification)


_Database (Storage Layer)-_

Preferred: PostgreSQL (good for location queries)

Alternative: MongoDB (simpler to start, flexible schema)


_Tables/Collections-_

Users
- user_id (PK)
- username
- points / badges

Reports
- report_id (PK)
- user_id (FK, optional)
- location_lat
- location_lon
- air_quality (enum: clear, dusty, smoky, polluted)
- allergens (array: pollen, mold, pet_dander, other)
- symptoms (array: sneezing, breathing_difficulty, headache)
- timestamp

_Visualization Layer-_

Map: Leaflet.js or Mapbox (pins for reports, color-coded by severity)


Charts: Chart.js / Recharts (allergen frequency, trends over time)






_Data Flow (Step-by-Step)-_

User submits a report via app → form data sent to Backend API (POST /report).


Backend validates & stores in Database (PostgreSQL/MongoDB).


Other users request data (map view, charts) → app sends GET /reports.


Backend queries database and aggregates → returns JSON.


Frontend displays results as interactive maps + charts.


Gamification service updates user points/badges after submissions.

	[ User (Student) ]
	       |
	       v
	[ Frontend (Web/Mobile App) ]
	       |
	       v
	[ Backend API (Node.js / Flask) ]
	       |
	       v
	[ Database (PostgreSQL / MongoDB) ]
	       |
	       v
	[ Visualization Layer (Maps + Charts) ]


_Reports-_

Audio or text reports

Text reports:

If location is on. Else user enters a general description of their location (cobham, hersham, near odeon kingston etc.)

Air quality: drop down menu of options

Allergens: another drop down menu with options + “other” where user enters a response into a text box

Symptoms: another drop down menu with options + “other” where user enter response into a text box\

Take timestamp of when DB receives report

Audio:

Take subtitles of the user’s words analyse keywords through Natural Language Processing

