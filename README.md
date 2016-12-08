# Open Identifier

Open Identifier is a project which attempts to solve an issue which plagues the advertising industry:  How to integrate two different ad systems which use different identifier for members of their viewing audience.

Currently, the way that this is solved is through a process called "cookie mapping".  The process of cookie mapping is as follows:

1. Company A wants to integrate with Company B, so they agree to a "partnership"
2. Company A adds a beacon to their online artifacts (ads, scripts, etc.) which calls a URL owned by Company B
3. The user identifier and partner identifier are sent to Company B - e.g. `http://company-b.com?partner=company-a&id-abcdefg&redirect=company-a.com?id=abcdefg&company-b-id=`
4. Company B redirects back to Company A with their user ID via a 302 redirect - e.g. `http://company-a.com?id=abcdefg&company-b-id=1234567`
5. Now, both Company A and Company B have the audience member's ID from both companies.

The problem with this method is that there is a growing number of ad companies, and these companies partner with lots of other companies.  What seems like a straightforward solution for two companies becomes complex as the number of companies grow.  For example, if Company A worked with 7 other companies, there would be a total of 54 requests, whereas if each company just worked with a central hub, there would be 16 requests, less than 1/3 the amount of web traffic:

!(https://docs.google.com/drawings/d/1lxv1EKDxpBSKkesH-UU7MVLfhGg8PBWuljZblBTUtoY/pub?w=1106&h=580)[cookie mapping spoke vs. wheel visualization]

The following are benefits:

1. Faster rendering of pages/apps and ads
2. Greater coverage of data
3. Easier server side integrations (like with Server Side Header Bidding)

The Open Identifier domain would perform the following functions:

1. Store the audience member's ID in the cookie space of the browser for its domain (open.identifier.online)
2. Generate a new ID for a member that does not yet have an ID
3. Redirect to the calling script the Open Identifier for the audience member if it can be determined

There is nothing stored on any server that powers the Open Identifier domain.

The code that is running on the domain is included in this project, and is open source, with the MIT license.

