Khabar Bondhu (KindMeal)

AI-Powered Food Donation and Redistribution Platform

  *Reducing Food Waste, Sharing Hope, Building a Better Future.*

📌 Project Overview :

Khabar Bondhu (“Friend of Food”) is a web platform that rescues edible surplus food, brings less known institutions like small madrasas and orphanages into the limelight for donors, and allows donors to donate without any trouble, with all the transparency possible. Food providers (bakeries, shops, and events) put up surplus food on the website, volunteers pick up the food, and institutions acknowledge how much they received. People willing to help but too busy for that can get the whole process of donating managed by the team, after which a report will be provided to them with details and delivery proof. Three AI features support the platform: OCR-based expiry-date detection with safety flags, smart donor-to-institution matching, and a Bangla chatbot.

📌 Problem Statement:

There is excess packaged food close to expiry in many bakeries and stores. Moreover, food in excess remains after parties or weddings. On the other hand, many madrasas and orphanages do not come into the knowledge of donors and get less regular donations. Donors, willing to donate, don’t have the time to find a reliable institution, coordinate food provision and make sure that it has been done. No existing platform for donating food, whether international or local, provides food donation, lesser-known yet reliable institutions, donation by the donor with full transparency and Bangla language AI facility. (Invisibility of lesser-known institutions is an initial observation by us, which we will verify through a field study during the pilot stage.)

📌 Objectives:

•	Build a web platform that connects food donors, verified institutions, and donors who want to give but cannot manage the process themselves.
•	Reduce avoidable food waste by rescuing safe packaged food and event surplus and delivering it to institutions in need.
•	Make lesser-known institutions visible through verified profiles and a Need Map.
•	Provide OCR-based expiry-date detection with safety flags that go to a human for review.
•	Match donations and donor budgets to suitable institutions using an AI-assisted matching feature.
•	Provide a Bangla AI chatbot so non-technical users can use the platform in their own language.
•	Provide transparency through records of collection, delivery and spending, with status updates to donors.
•	Deliver a complete, deployed system with frontend, backend, database, authentication, AI integration, testing and documentation within the semester.

📌 Scope of the Project:

In scope: A responsive web application (React.js frontend, Node.js and Express.js backend, PostgreSQL database, Python FastAPI AI service) with five user roles and these modules: Food Rescue, Institution Connect, Managed Giving, Need Map, and an Admin dashboard. The three core AI features (OCR expiry-date detection, donor-to-institution matching, Bangla chatbot), notifications, activity logs, online deployment, testing and documentation are also in scope. 
Out of scope:
•	An online payment gateway. Donors pay outside the platform, and the Admin records the payment reference.
•	A native mobile app. The system is a responsive website that works on phones.
•	Route optimisation, need analysis from institution requests, fraud and anomaly detection, demand prediction, and AI impact analysis. These are future work.
•	Legal registration of an organisation and any official food-safety certification. The AI only flags items, and a person makes the final safety decision.
•	Onboarding real partner shops and institutions beyond what is needed for a demonstration with sample data.

📌 Definitions and Abbreviations:

Term	Meaning:
SRS :	Software Requirements Specification, this document.
FR / NFR : Functional Requirement / Non-Functional Requirement.
Food Partner :	A bakery, shop or event organiser that lists surplus food.
Institution :	A madrasa, orphanage or similar organisation that receives food or support.
Verification level :	Identified (found and recorded), Verified (checked on site by the team), or Partner (agreed to take part regularly).
Managed Giving :	A service where the team carries out a donor’s donation and reports on it.
Need Map :	A map showing the general areas of verified institutions and their needs.
OCR :	Optical Character Recognition: reading text, such as an expiry date, from a photo.
Safety flag :	A label (OK to proceed, Near expiry, Expired, Needs review) given to a checked food item.
AI Service :	The separate Python FastAPI service that performs OCR, matching and chatbot tasks.
JWT	: JSON Web Token, used to keep a user logged in securely.
REST API :	A web interface through which the frontend and backend exchange data in JSON.

📌 Assumptions and Constraints:

Assumptions:
•	Users have internet access and a smartphone or computer with a modern browser.
•	Admins and volunteers are available to do field verification and to review flagged food.
•	Food partners and institutions give accurate information, which the team checks during verification.
•	The demonstration uses sample data and test accounts.
•	Access to the Gemini or OpenAI API and to an OCR tool is available within free or low-cost limits.

Constraints:
•	The project must be finished within one semester by a team of four.
•	Free-tier hosting and API quotas may limit speed and usage.
•	AI must never be the final decision-maker on food safety. Flagged items need human review.
•	Any real-world use must follow the Bangladesh Safe Food Act 2013 and the guidance of the Bangladesh Safe Food Authority.
•	The exact address and personal details of institutions, especially those housing children, must not be shown publicly.
•	The core technology stack is React.js, Node.js with Express.js, PostgreSQL, and Python with FastAPI.

📌 2. Functional Requirements:

Requirements are numbered FR-01 onward. Priority “Must” means the feature is needed in the semester version. “Should” means it is planned but can be dropped if time runs short.

i. Account and Access Management

FR-01	Users can register with name, email or phone number, password and a role (Donor, Food Partner, Institution Representative or Volunteer).	Must
FR-02	The system validates registration data and rejects duplicate emails or phone numbers.	Must
FR-03	Registered users can log in securely, and the system issues a session token.	Must
FR-04	Users can log out, which ends the session.	Must
FR-05	Users can view and update their own profile and change their password.	Must
FR-06	The system limits each feature to the roles allowed to use it (role-based access control).	Must
FR-07	The Admin can view, suspend, reactivate and delete user accounts.	Must
FR-08	Users can reset a forgotten password through email.	Should

ii. Institution Connect

FR-09	An Institution Representative can create an institution profile with name, type (madrasa, orphanage or other), general area, contact person, number of residents or students, and whether it is residential.	Must
FR-10	An Institution Representative can add, edit and close needs (food, essential items or education items) with quantity, estimated budget, urgency and frequency.	Must
FR-11	New institutions start at the level “Identified”. Only the Admin can raise a level to “Verified” or “Partner” after a field check.	Must
FR-12	The Admin can record verification details: date, verifier name and notes.	Must
FR-13	Users can browse and search institutions by area, type, need, urgency and verification level.	Must
FR-14	The system shows the verification level on every institution profile and in every list.	Must
FR-15	The system shows only the general area of an institution publicly. The exact address and personal contacts are visible only to the Admin and to the volunteer assigned to a delivery.	Must

iii. Food Rescue

FR-16	A Food Partner can register business details (name, type, area, address and contact).	Must
FR-17	A Food Partner can create a food listing with food type, quantity, packaging, expiry date, pickup time window and pickup address.	Must
FR-18	A Food Partner can edit or cancel a listing that has not yet been picked up.	Must
FR-19	Volunteers can view available listings in their area.	Must
FR-20	A Volunteer can accept a pickup task, and the system then marks the listing as reserved.	Must
FR-21	A Volunteer can release an accepted task, and the listing becomes available again.	Must
FR-22	If no volunteer accepts a listing within a set time, the system notifies the Admin.	Should
FR-23	A Volunteer can update the pickup status (picked up, delivered) and upload a photo as delivery proof.	Must
FR-24	An Institution Representative can confirm that delivered food was received.	Must
FR-25	The system keeps a record of every collection and delivery with quantity, date, source and destination.	Must

iv. AI-Assisted Features

FR-26	Volunteers can upload a photo of a food package to the OCR service.	Must
FR-27	The OCR service reads the expiry or best-before date and shows it to the user, who can correct it before saving.	Must
FR-28	The system gives each checked item a safety flag: OK to proceed, Near expiry, Expired, or Needs review (unreadable or low confidence).	Must
FR-29	Items flagged Near expiry, Expired or Needs review go to a review queue where the Admin approves or rejects them with a reason.	Must
FR-30	The system does not allow expired or rejected items to be assigned for delivery.	Must
FR-31	The system can suggest a ranked list of verified institutions for a food listing, using food type, quantity, location, urgency, recorded needs and recent support received.	Must
FR-32	The Admin or Volunteer can accept or change a suggested institution, and the system records the final choice with the suggestion’s score and reason.	Must
FR-33	The system can suggest verified institutions to a Donor based on the Donor’s budget and preferences.	Should
FR-34	Users can ask the chatbot questions in Bangla (or English) about donating, current needs, accepted food types and how to use the platform.	Must
FR-35	The chatbot answers from platform information, politely declines questions outside its scope, and never certifies food as safe.	Must
FR-36	The system stores chat messages so users can see earlier conversations.	Should

v. Managed Giving

FR-37	A Donor can create a donation request by choosing an amount or purpose, an institution (or asking for a suggestion) and a preferred date.	Must
FR-38	Before confirming, the system shows the Donor an estimated cost breakdown (food or items, transport, packaging and any service fee).	Should
FR-39	The Admin can review, accept or reject a donation request and assign volunteers to deliver it.	Must
FR-40	The Admin can record the donor’s payment reference (payment is made outside the platform) and mark the funds as received.	Must
FR-41	The Admin can record each expense with category, amount, description and receipt photo.	Must
FR-42	A Donor can track the status of a donation: Requested, Accepted, In Progress, Delivered or Completed.	Must
FR-43	A Donor can ask to attend the delivery, and the request is shown to the Admin.	Should
FR-44	The system generates a completion report showing items, costs, delivery proof and any unused amount.	Must
FR-45	A Donor can view their donation history.	Must

vi. Need Map

FR-46	The system shows an OpenStreetMap map with markers for verified institutions at general-area level.	Must
FR-47	Users can filter map markers by need type, urgency and verification level.	Should
FR-48	Selecting a marker shows a summary of the institution’s needs with a link to donate.	Should

vii. Notifications, Reports and Administration

FR-49	The system sends in-app notifications when the status of a listing, pickup, donation or verification changes.	Must
FR-50	The Admin dashboard shows pending verifications, flagged food items, active pickups, open donation requests and summary counts.	Must
FR-51	The Admin can view and export activity reports (items rescued, donations completed, institutions supported).	Should
FR-52	Users can report a problem with a listing, institution, delivery or donation, and the Admin can review the report and record the outcome.	Must
FR-53	The system logs important actions (verification, flag review, expense entry, account changes) with the user and time.	Must

📌3. Non-Functional Requirements:

NFR-01	Performance	Pages should load within 3 seconds under normal use on a typical mobile connection.
NFR-02	Performance	OCR and chatbot responses should be returned within 10 seconds under normal conditions.
NFR-03	Usability	The interface must be responsive and work on desktop, tablet and mobile screens.
NFR-04	Usability	Main tasks, such as listing food or requesting a donation, should take no more than five steps, with clear labels and error messages.
NFR-05	Usability	The interface must display Bangla text correctly (Unicode support).
NFR-06	Security	User passwords must be hashed (for example with bcrypt) and never stored as plain text.
NFR-07	Security	Logins use tokens that expire, and every protected request is checked on the server for the user’s role.
NFR-08	Security	The deployed system must use HTTPS.
NFR-09	Security	API keys and database credentials must be kept in environment variables and never committed to GitHub.
NFR-10	Security	User input must be validated, and database queries must be parameterised to prevent injection attacks.
NFR-11	Privacy	Exact institution addresses and personal data of children must not be displayed publicly, and only necessary personal data is collected.
NFR-12	AI safety	AI output on food safety is advisory. Items flagged by the AI must be reviewed by a person before being accepted or rejected.
NFR-13	Reliability	If the AI service is unavailable, core features (listings, pickups, donations) must keep working, and the user sees a clear message.
NFR-14	Availability	The deployed system should be available online during the evaluation period, depending on the hosting platforms’ uptime.
NFR-15	Scalability	The database and APIs should allow more cities and areas to be added without redesign.
NFR-16	Maintainability	The frontend, backend and AI service are separate modules with documented APIs, and code is committed regularly with meaningful messages.
NFR-17	Auditability	Key actions are recorded with user and time so that verification and spending can be traced.
NFR-18	Compatibility	The system should work on current versions of Chrome, Edge, Firefox and Chrome for Android.

📌 4. User Roles:

The system has five user roles. The four roles other than the Admin are called Platform Members in the use case diagram because they share the same account, chatbot and problem-reporting features.

(i) Admin:
A team member who runs the platform.

Responsibilities:
•	Manage user accounts
•	Verify institutions and set verification levels
•	Review food items flagged by the AI
•	Accept donation requests, record payments and expenses
•	Resolve complaints
•	Monitor the dashboard and generate reports

(ii) Donor:
An individual or company that wants to give food or money.

Responsibilities:
•	Browse institutions and the Need Map
•	Receive institution suggestions based on budget and preferences
•	Request and track managed donations and view reports
•	Use the Bangla chatbot and report problems

(iii) Food Partner:
A bakery, shop or event organiser with surplus food.

Responsibilities:
•	Register business details
•	Create, edit and cancel food listings
•	Follow the status of their listings
•	Use the chatbot and report problems

(iv) Institution Representative:
A person who represents a madrasa, orphanage or similar institution.

Responsibilities:
•	Create and update the institution profile and its needs
•	Confirm receipt of delivered food
•	Use the chatbot and report problems

(v) Volunteer:
A person who collects and delivers food.

Responsibilities:
•	View available listings and accept pickup tasks
•	Check packages with the OCR feature
•	Update pickup status and upload delivery proof
•	Browse institutions, use the chatbot and report problems
AI Service (system component): The AI service is not a user. It performs OCR, matching and chatbot tasks for the platform, and its results are always reviewed by a person where safety is involved.

📌 5. Use Cases
Each use case lists the actor, what the actor does, and how the system responds. The numbers match the use case diagram, which is submitted as a separate file.

UC-01: Register Account
Actor :	Donor, Food Partner, Institution Representative or Volunteer
Precondition :	The user does not have an account.
Action :	The user opens the registration page, enters name, email or phone, password, and chooses a role.
System Response :	The system validates the data, rejects duplicates, stores the account with a hashed password, and confirms the registration.

UC-02: Log In
Actor	: Any registered user
Precondition :	The user has an account.
Action :	The user enters email or phone and password.
System Response :	The system checks the credentials, issues a session token and opens the dashboard for the user’s role. If the credentials are wrong, it shows an error and does not log in.

UC-03: Manage Institution Profile and Needs
Actor :	Institution Representative
Precondition	: The user is logged in.
Action : The user creates or edits the institution profile and adds or updates needs.
System Response	: The system saves the information, sets the level to Identified for a new institution, and shows the needs to other users.

UC-04: Verify Institution
Actor :	Admin
Precondition : An institution is at level Identified and a field check has been done.
Action :	The Admin reviews the institution, enters the field-check details and sets the level to Verified or Partner.
System Response :	The system records the date and verifier, updates the level shown publicly, and notifies the representative.

UC-05: Browse Institutions and Need Map
Actor :	Donor, Volunteer
Precondition :	The user is logged in.
Action :	The user searches or filters institutions, or opens the Need Map and selects a marker.
System Response :	The system shows matching verified institutions with general area, needs and verification level, and hides exact addresses.

UC-06: List Surplus Food
Actor :	Food Partner
Precondition :	The user is logged in with a partner profile.
Action :	The user enters food type, quantity, packaging, expiry date, pickup window and address.
System Response :	The system validates the data, saves the listing as Available, shows it to volunteers and confirms to the partner.

UC-07: Check Expiry Date (OCR)
Actor :	Volunteer (included in UC-09)
Precondition :	A pickup is in progress and a photo of the package is available.
Action :	The volunteer uploads the photo.
System Response :	The AI service reads the expiry date. The system shows it for correction and assigns a safety flag. If the result is unclear, the item is marked Needs review.

UC-08: Review Flagged Food
Actor :	Admin
Precondition :	An item is in the review queue.
Action :	The Admin opens the item, looks at the photo, date and flag, and approves or rejects it with a reason.
System Response :	The system updates the item status, excludes rejected or expired items from delivery, and notifies the volunteer and the food partner.

UC-09: Accept and Complete Pickup
Actor :	Volunteer
Precondition :	A listing is available and has passed the safety check.
Action :	The volunteer accepts the task, collects the food, checks it (UC-07), marks it picked up and then delivered with a proof photo.
System Response	: The system reserves the listing, updates the status at each step, records the collection and delivery, and notifies the food partner and the institution.

UC-10: Confirm Receipt of Food
Actor :	Institution Representative
Precondition :	A delivery has been marked as delivered.
Action :	The representative opens the delivery and confirms receipt, or reports a problem.
System Response :	The system records the confirmation, marks the pickup complete and notifies the volunteer and the Admin.

UC-11: Get Institution Match Suggestion
Actor : Admin, Donor
Precondition :	A food listing needs an institution, or a donor is choosing where to give.
Action : The user asks for suggestions.
System Response :	The AI service ranks verified institutions using food type, quantity, location, urgency, needs and recent support. The system shows score and reason, lets the user accept or change the choice, and records it.

UC-12: Request Managed Donation
Actor :	Donor
Precondition :	The user is logged in.
Action :	The donor chooses an amount or purpose, an institution (or asks for a suggestion) and a preferred date, and may ask to attend the delivery.
System Response : The system shows an estimated cost breakdown, saves the request as Requested and notifies the Admin.

UC-13: Process Donation and Record Expenses
Actor :	Admin
Precondition :	A donation request exists.
Action :	The Admin reviews and accepts the request, records the donor’s payment reference, assigns volunteers and records each expense with a receipt.
System Response :	The system updates the status, stores the expense records and notifies the donor at each stage.

UC-14: Track Donation and View Report
Actor :	Donor
Precondition : The donor has made a donation request.
Action :	The donor opens the donation history or a donation’s details.
System Response :	The system shows the current status, expenses and delivery proof. After completion it generates a completion report with any unused amount.

UC-15: Ask Bangla Chatbot
Actor :	Donor, Food Partner, Institution Representative, Volunteer
Precondition :	The user is logged in.
Action :	The user types a question in Bangla or English.
System Response :	The AI service replies using platform information. It declines questions outside its scope, never certifies food as safe, and the system stores the conversation.

UC-16: Report a Problem
Actor :	Donor, Food Partner, Institution Representative, Volunteer
Precondition :	The user is logged in.
Action :	The user selects a listing, institution, delivery or donation and describes the problem.
System Response :	The system saves the complaint, confirms it to the user and notifies the Admin.

UC-17: Manage Users
Actor :	Admin
Precondition :	The Admin is logged in.
Action : The Admin searches for a user and suspends, reactivates or deletes the account.
System Response:	The system updates the account status, blocks login for suspended users and logs the action.

UC-18: Resolve Complaints
Actor :	Admin
Precondition :	A complaint has been submitted.
Action :	The Admin opens the complaint, looks into it and records the outcome.
System Response :	The system updates the complaint status, notifies the reporter and logs the action.

UC-19: View Dashboard and Reports
Actor:	Admin
Precondition :	The Admin is logged in.
Action : The Admin opens the dashboard or asks for a report for a period.
System Response :	The system shows pending verifications, flagged items, active pickups, open donations and counts, and generates a report that can be exported.



🎯 All users, including the Admin, log in through UC-02 before using the other use cases. UC-07 is included in UC-09. UC-08 extends UC-07 when an item is flagged. UC-11 extends UC-12 when a donor asks for a suggestion.


All users, including the Admin, log in through UC-02 before using the other use cases. UC-07 is included in UC-09. UC-08 extends UC-07 when an item is flagged. UC-11 extends UC-12 when a donor asks for a suggestion.
