GOOGLE SUMMER OF CODE 2017

**Implementing R****ole-based permissions in Mifos Android Client App**

**Abstract**

Android client for Mifos X allows the bank staff to manage the client details and records at any time remotely with both offline and online support. Mifos has already released the documentation having set of APIs needed to finish the app and I propose to implement a role-based permissions feature which will add up a layer of security to the transactions made by field agents for the clients and will help in authorized activation of different services.

**Problem Statement****   **

Financial security and fraud prevention are of utmost importance for any company. The process of creating a loan, client and transaction entry by the field agents is not supervised. Agents have unrestricted access to modify data and sensitive information which is a potential vulnerability. Due to lack of tracking, identification, and verification, there are chances of internal and external frauds which could lead to monetary losses.

**Proposed Solution**** **

The proposed implementation will enable role-based permissions in the application and will help in having a verification by higher authorities for all the critical transactions. This will enable multiple officers in the organization having different roles, that will be validating documents for clients, loans, saving accounts, groups, centers before approval.

**Benefits**

For the organization, it will introduce an additional level of verification for documents before accessing bank utilities for activating any service for the client.

For the clients, it is ensuring that the loan has been sanctioned after proper verification which ensures a good level of security. This will reduce the chances of fraudulent cases or human error by the field agent.

**Project Goals**** **

These are the goals of the project which would help reduce the risk of fraudulent activities and errors.

* Role-based permissions - At first, role-based permissions need to be implemented for the existing modules and new proposed modules for the client, loan, saving account, group and center.

* Activation, updating, deletion, rejection, reactivation, the closing of a client should be implemented.

* Assigning and unassigning staff to a client need to be implemented.

* Loan Approve, reject, withdraw, rescheduling request, rescheduling approval, and rejection should be implemented.

* Saving account approval, rejection, withdrawal of request and closing of an account will be implemented as new modules.

* Group activation, updating, deletion, closing needs to be implemented.

* Center activation, updating, deletion, closing needs to be implemented.

* Filter option in client list, group list, center list based on activated, deactivated needs to be implemented for ease in finding deactivated or activated entities.This feature is helpful in case a officer is assigned a job of activating clients, centers, groups.

**Technical Implementation details-**

* **Implementation of Role based permissions-**

    * At first, Some new roles need to be defined and based on role permissions should be assigned using Restful API - 

        * Create new roles - > Update a role’s permission - > Create users with different roles. 

        * Create new roles -  POST [https://DomainName/api/v1/roles](https://domainname/api/v1/roles) 

        * Create new user and assign roles - POST https://DomainName/api/v1/users

    * On the Dashboard Activity a rest API for getting user/staff permissions will be called and the permissions will be stored in the SQLite table by 

        * Retrieve user roles - > Retrieve roles permissions

        * Retrieve user - GET https://DomainName/api/v1/users/{userId} 

        * API endpoint to Retrieve a roles permissions - 

GET [https://DomainName/api/v1/roles/{roleId}/permissions](https://domainname/api/v1/roles/%7BroleId%7D/permissions)

    * Data Manager class for managing permissions API, DataManagerPermissions needs to be implemented that will have methods that in response get API observable response using retrofit2.

    * PermissionService - Interface for retrofit GET, POST or PUT methods depending upon different APIs.

	

	Retrieve a user - 

@GET("suburl here")

	Observable<StaffData> getUserDetails(@Query("userId") int userId);

	

	Retrieve a user’s role permissions -

	@GET("suburl here")

	Observable<PermissionData> getRolePermissions(@Query("roleId") int roleId);

    * Based on the permissions, various UI elements will be disabled/enabled or visible/gone.

* **Addition of sub-modules in Client, Loan, Group, Center and Savings -**

    * Activate/Approve - Activation/Approving is already implemented in all the modules, but It is required to sync role based permissions. Activate checkbox/button will be visible depending upon permissions assigned to a particular user.

    * Updating, deleting, rejecting, reactivating, closing, withdrawing, rescheduling,- These are the new modules to be implemented along with rest API calls. All the sub modules will have similar architecture and will have just some design and implementation changes on UI and attributes.

        * Data Manager classes for client, center, group, loan and savings will have more methods that in response provide API observable response using retrofit2.

        * Service classes for client, center, group, loan, savings - Interface for retrofit GET, POST or PUT methods depending upon different APIs.

        * Creation of object POJO classes for getting response from end APIs will be developed for all the sub modules.

        * Toggle buttons and other UI elements will be implemented to enable updating, deleting, rejecting, reactivating, closing, withdrawing, rescheduling.

        * Testing of these sub modules with various users with different roles will be tested.

* **Filter list in client, center, group list **

    * End api calls has already been implemented to get the client, center and group list, To provide filtering functionality a spinner will be implemented that will have activated/approved, deactivated/not approved and all options and based on this we will send a parameter to the API and the list will be sorted.

    * This need some changes in Service classes and some extra parameters will be send based the case, like client_status, group_status, center_status can be used with value activated, rejected, deactivated, etc.

    * This needs a spinner in all the 3 fragments CenterListFragment, ClientListFragment, GroupListFragment and some slight changes in the view classes to pass an extra parameter to the service interface.

**Project Timeline** **Official Coding Period**

GSOC officially provides 12 weeks to code and work on the project. In every 2 weeks, I will get mentors feedback on the code quality and design architecture as well as on UI/UX. In all the new and existing modules I will work with service interfaces, data-manager, model & presenter classes to implement role-based permissions wherever it’s needed and end API calls for some specific features. Writing documentation and testing with mock data-manager providers will be a necessary activity in each week.

* **Week 1 ( 30th May - 5th June )**

    * Implementation of role-based permissions architecture.

    * Understanding the architecture of client module.

    * Implementation of client activation, client update and delete feature.

* **Week 2 ( 6th June - 12th June )**

    * Implementation of closing, rejecting, reactivating client.

* **Week 3 ( 13th June - 19th June )**

    * Implementation of modules related to assignment and unassignment of staff to/from a client. 

    * Writing documentation for client module.

* **Week 4 ( 20th June - 26th June ) **

    * Time to clear backlogs, implement feedback/changes proposed by mentors.

    * Writing Unit Test cases for client modules.

* **Week 5 ( 27th June - 3rd July )**

    * Understanding the architecture of loan module.

    * Implementing of Approval, withdrawal, and rejection of loan application.

* **Week 6 ( 4th July - 10th July )**

    * Creating new loan reschedule request along with approving loan reschedule and reject loan reschedule components.

    * Writing documentation for loan module.

* **Week 7 ( 11th July - 17th July )**

    * Understanding the architecture for group module.

    * Implementation of activating, deactivating, deleting and closing of the group.

* **Week 8 ( 18th July - 24th July )**

    * Understanding the architecture and working structure of the center module.

    * Implementation of Activation, updating, deletion, and closing of center.

* **Week 9 ( 25th July - 1st August ) - Work on Evaluation 2**

    * Time to clear backlogs, implement feedback/changes proposed by mentors.

    * Writing documentation for group and center modules.

    * Writing unit test cases for the group, center modules.

* **Week 10 (2nd August - 8th August )**

    * Understanding the working architecture for savings module.

    * Implementation of approving, rejecting, withdrawal, and closing of Saving Application. 

    * Writing documentation for saving module.

    * Writing unit test cases for saving module.

    * Testing and debugging of Saving module along with all the other modules.

* **Week 11 (9th August - ** **15th August )**

    * Implementation of filter feature in client list, group list, center list

    * Writing and improving documentation

    * Testing and debugging with different cases

    * Updating unit test cases

* **Week 12 ( 15th August - 21st August ) Final Evaluation Week**

    * Time to clear backlogs, implement feedback/changes proposed by mentors.

    * Improvements in documentation and test cases of all the implemented modules.

    * Testing of the whole app with different role-based permissions and debugging.

**About Me**

* **Why are you the right person for this project:**

Last year, I pursued my summer internship from Elanic, Bangalore and there I learned the Implementation of Model-View-Presenter architecture, I worked on an Application that helped in automation of order status updating and checking order details, I implemented a custom barcode scanner and used RxJava and RxAndroid for implementation of it.

Here is the link for RxJava Implementation - 

[https://github.com/CodeNicely/BunchOfFoolsApp/blob/master/app/src/main/java/app/bunchofools/codenicely/project/spot_upload/presenter/UploadSpotPresenterImpl.java](https://github.com/CodeNicely/BunchOfFoolsApp/blob/master/app/src/main/java/app/bunchofools/codenicely/project/spot_upload/presenter/UploadSpotPresenterImpl.java)

Here is another Project with MVP Architecture and Retrofit Implementation -

[https://github.com/CodeNicely/GroceryApp](https://github.com/CodeNicely/GroceryApp)

* **If in college, the current area of study:**

B.Tech in Computer science and Engineering from NIT Raipur, currently studying in 3rd year.

* **Contact information and preferred method of contact:**

Email: [meghal.nit@gmail.com](mailto:meghal.nit@gmail.com)

Gitter Id: @meghalagrawal

Telephone number: +91 8109109457

Time zone: UTC +05:30

Skype Id: meghal.nit

Preferred method: Email, gitter or telephonic call

* **Career Goals:**

I am seeking to start a company on my own and contribute to the community.I aspire to work with a collaborative team of talented individuals and produce work that can functionally and potentially serve the needs of the clients.Taking a step forward, I recently took an initiative and started a developing club, to guide the students on how to get exposure to real-world projects and experience of working with the team on big projects.Completing that as my near term goal, I will prepare myself to take on expanded roles and responsibilities in the future.

* **Please share any links to source codes you have written or websites you have built:**

I have developed apps for some real world problems that are live on play store. I am also an avid Open Source lover and the source code to most of my apps can be easily found on my GitHub profile which help me to guide my juniors and classmates about the way I learn and implement.

Github profile link - [https://github.com/meghalagrawal](https://github.com/meghalagrawal)

	Grocery Android App - An app for a grocery based startup from Jaipur.

	Github link - [https://github.com/CodeNicely/GroceryApp](https://github.com/CodeNicely/GroceryApp)

	

	Bunch of fools App - An app for Clean India Movement for a local NGO

	Github link - [https://github.com/CodeNicely/BunchOfFoolsApp](https://github.com/CodeNicely/BunchOfFoolsApp)

1Mile App - An app for a startup focuses for different things within a mile.

	Github link - [https://github.com/CodeNicely/ChatAroundApp](https://github.com/CodeNicely/ChatAroundApp)

	

	Python based Server end using Flask framework -

	1Mile App server end GitHub link - [https://github.com/CodeNicely/LocationServer](https://github.com/CodeNicely/LocationServer)

* **If you have visited our gitter chat room, what nickname did you use?**

	My gitter id is - @meghalagrawal

	Name I used - Meghal Agrawal

* **Have you contributed to other open source projects? If so which?**

I have worked on my own projects ideas by making teams, building those ideas as open source project during development in either Github or Bitbucket.

* **Have you any previous experience with Javascript/Java/Spring/Hibernate/Mysql**

    * Javascript - I have experience with javascript as I have worked on a website where I used JS and ajax to call REST API endpoints.

Unfortunately, I lost all my commit records while using git push --force for one of the live website in which I was a part of the Team - [http://www.mpenavmo.com](http://www.mpenavmo.com)

The repository link is here - [https://github.com/CodeNicely/navmo](https://github.com/CodeNicely/navmo)

    * Java - I learned java with the experience as I am actively involved in developing Android projects.

    * Mysql - I have used Mysql with Django and native PHP while working on server end for Android apps as well as for a Website 

Offercart Server end - [https://github.com/CodeNicely/OfferCartServer](https://github.com/CodeNicely/OfferCartServer)

* **What other commitments do you have this summer? **

For this summers my primary commitment is Google Summer of Code and I will be able to give at least 30 - 40 hours a week for the project. I will work 5 hours on weekdays and 8 hours on weekends.

I have my college starting from 5th July 2017. No other commitments, I just want to work on GSOC project so that I can get exposure to new challenges and best open source project.

* **Have you deployed and run the platform?**

Yes, I have already built the Android client app and self-service app and I have even submitted some PRs and issues after some commits.

	

* **Have you submitted any patches or source code to Mifos X yet? Please provide links to the commit in Github?**

Yes, I have added some pull requests in the Android client app for Mifos X. Here are the links -

	

* [https://github.com/openMF/android-client/pull/647](https://github.com/openMF/android-client/pull/647)

* [https://github.com/openMF/android-client/pull/588](https://github.com/openMF/android-client/pull/588)

* **Have you previously participated in Google Summer of Code?**

	No, this is the first time I am applying for GSOC.

* **Are you applying to multiple organizations this year?**

	No, I am just applying for Mifos X.

