## PostGraphile Backend Code challenge

This challenge gets you familiar with Postgraphile, a GraphQL/Postgres database connector written in NodeJs.

<https://www.graphile.org/postgraphile/quick-start-guide/>
<https://www.graphile.org/postgraphile/usage-library/#http-middleware>

### The challenge

The challenge is to design a basic data model using PSQL and API using Postgraphile for creating and managing a basic meetings system in GraphQL.

The user should be able to create meetings with 1+ participants, and store basic information about a Meeting (for example the date of the meeting, a simple title and agenda, and maybe a Zoom or MSTeam's URL for virtual meetings). It should be able to store and reference the people who are attending the Meeting and allow participants to fetch their meetings.

### First steps

After setting up a Postgres server and installing NodeJs, define your schema and experiment with the API already provided by Postgraphile. 

You may initially choose to run the server in CLI mode but a more expandable option would then be to run this same schema direct from a node file in 'library mode' <https://www.graphile.org/postgraphile/usage-library/>.

### Next steps

From here, you can choose how to expand the functionality of the API in different ways (note these are only ideas on next steps, you can choose diferently or expand in a different direction);

- You may wish to filter out past meetings, so users can easily get their next meeting.

- You may want to improve the meetings data-model to allow 'recurring meetings' that occour every week/month.

- If your ambitious you could even allow participants to accept or confirm their attendance.

- You could even provide a seperate iCal feed for the user to add their appointments into Outlook or another calendar tool.
