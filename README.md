# msa-power-apps-pickle

## About
Pickle is a lucnhtime buddy finder/casulal networking Power App for those who work in big organisations and what to meet new people from different depratmernts or are simply looking for a lunchtime jog buddy.

## Investigating target users and problem context with PACT analysis
To study the context of the proposed app and try to understand target users, it is best to use a structured framework like PACT (see [here](http://hci.ilikecake.ie/requirements/pact.htm) for details). PACT framework suggests the app is discussed in the context of **P**eople (target users), relevant **A**ctivities those people undertake, **C**ontext of such activities and **T**echnologies used. I omitted the full analysis to keep this brief but the guiding questions I tried to answer included:

* Who are the users? (Demographics, employment etc.)
* What is their level of tech proficiency?
* What motivates, pleases and engages the users, in particular with the current apps they use?
* Are we looking at frequent or infrequent users?
* What are the users' goals, tasks and actions?
* How are they currently performing those tasks? On what devices?
* Are these activites memorable? Are they done often?
* What is the social and organisational context of these tasks? How are similar tasks handled in the workplace - this is particularly important to discuss for a social app.

## Target persona
Ideally, the process of creating a persona would involve the target users themselves, for example through surveys and user stories. At this stage, this is not possible but any further development should definitely involve a more user-centric approach.

Based on PACT analysis, our target persona looks something like this:

<table>
  <tr>
    <th>Persona </th>
    <th>Description</th>
  </tr>
  <tr>
    <td><img src="stock-photo-young-professional.jpg" alt="stock photo of a young professional"></td>
    <td>James, 25, is a junior marketing specialist at a large tech company in Sydney. He has been at this company for three years, ever since he graguated.  James is tech-savvy and spends a lot of time on his phone. He checks Facebook, Instagram and LinkedIn daily on his smartphone on the way to work, during the day when he gets bored and in the evening. From time to time, he uses dating apps; he's tried both Tinder and Bumble. Internally, he uses Teams and Yammer, mainly to discuss work and contact people he doesn't know personally to ask specialist questions. He likes the simplicity of these interfaces and finds it easy to remember what to do when he hasn't used them in a long time (especially with the occasional use apps). James socialises with his colleagues regularly, ususally by grabbing a coffe after the morning standup and occasionally over lunch. He likes to chat to his immediate teammates during the day and always attends lunch-and-learns when he has the time.</td>
  </tr>
  <tr>
    <td colspan="2"><b>James's problem</b>: James likes meeting new people but has not had the opportunity to engage socially with people outside of his business unit. Though he is a social person and the company culture is friendly and welcoming, James finds himself unable to approach colleagues he does not know well because he does not want to bother busy people or senior colleagues. He expects that a lot of people at the company feel the same way. He knows most people in his business unit and occasionally grabs lunch with members of his team. However, more often than not he finds himself having solitary lunches, often due to everyones' differnt schedules and he wishes there was an easy way to meet someone outside his immediate business unit just for a chat.</td>
  </tr>
  <tr>
    <th width="50%">James's problem </th>
    <th>App functionality to address it</th>
  </tr>
  <tr>
    <td>James doesn't have a way of approaching someone he doesn't know at work and asking them to get lunch - some people might find it strange.</td><td>Pickle will pair James with another person or a group of people who are also looking for company. The group pairing feature is still under development.</td>
  </tr>
  <tr>
    <td>James would love to have more opportunities to talk to senior people about advancing his career.</td><td>Pickle has options to specify your level of seniority (in years of work) and, similarly, to select who you would like to meet.</td>
  </tr>
  <tr>
    <td>James loves learning from others and wishes there was a way to casually meet up with differnt specialists across the organisation, be that to ask some specific questions or just see what the work is like in the rest of the organisation.</td><td>Pickle lets you specify your business unit and select a particular business unit you are looking to meet people from.</td>
  </tr>
  <tr>
    <td>James goes for lunchtime jogs or gym classes from time to time and would like to have a lunchtime exercise buddy, but he doesn't know anyone interested.</td><td>Pickle isn't limited to finding food buddies - you can specify that you are looking for someone to join you for exercise.</td>
  </tr>
</table>

## Data sources
There are two dynamic data sources in the app, stored as Excel workbooks in OneDrive. The first, **Business Ares**, is a list of business areas of the company - it can be easily changed by a participating company to reflect the organisational structure; The second dataset. **Participants**, contains the details of users: choice of activity (qick coffee break, lunch or exercise), choice of how many buddies they want, their business unit and the business unit they would like to meet people from, their seniority (in years of work) and the seniority of people they would like to meet. When a new user enters their preferences, these are matched against the records in the database. If there is a match, the matching record is retrieved and removed from the database. If there are no matches, the new user record is added to the database for future matching.

To enable the complex data manipulations and allow the users to change their prefeernces before writing to the database, the app utilises a number Collections.

## Matching and messaging
When finding a buddy, the perfect matching is desired but is no always possible. Partial matching i senabled by prioritising user preferences:
* Choice of activity and Seniority are prioritised first - they have to match perfectly (i.e. the user's seniority has to be another user's desired seniority for the pairing to occur at all)
* Business unit is prioritised next
* Number of buddies is prioritised last; if there is no perfect match, the algorithm looks for matches without considering the desired number of buddies. If there is still no match, it tries without business unit preferences

Once matched, Pickle utilises Power Automate to enable the users to email their buddies straight from the app.

## App extensibility
### Scalability

### Future feature improvements
* In-app messaging
* A lunchtime window - the app should only function between 12pm-2pm to make it more lunchtime-specific and exciting for the users
* A feature to schedule another catch-up with the same person
* Use Office 365 to conenct to your organisation's user profiles
* A map and cafe API
* Accessibility
* Adding a check back later/push notification for when the match is found
* More sophisticated matching - eg allow to select different business units
* Ability to filter out seniorities 
* Send emails in-app and also email the person in the database to inform of the match - this was not possible due to student subscription but is very easy to implement

## Acknowledgements
<div>Icons in this app were made by <a href="https://www.flaticon.com/authors/mynamepong" title="mynamepong">mynamepong</a>, <a href="https://www.flaticon.com/authors/flat-icons" title="Flat Icons">Flat Icons</a>, <a href="https://www.flaticon.com/authors/ultimatearm" title="ultimatearm">ultimatearm</a> from <a href="https://www.flaticon.com/" title="Flaticon"> www.flaticon.com</a></div>

