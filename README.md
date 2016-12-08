# Open Identifier

Open Identifier is a project which attempts to solve an issue which plagues the advertising industry:  How to integrate two different ad systems which use different identifier for members of their viewing audience.

Currently, the way that this is solved is through a process called "cookie mapping".  The process of cookie mapping is as follows:

1. Company A wants to integrate with Company B, so they agree to a "partnership"
2. Company A adds a beacon to their online artifacts (ads, scripts, etc.) which calls a URL owned by Company B
3. The user identifier and partner identifier are sent to Company B - e.g. `http://company-b.com?partner=company-a&id-abcdefg&redirect=company-a.com?id=abcdefg&company-b-id=`
4. Company B redirects back to Company A with their user ID via a 302 redirect - e.g. `http://company-a.com?id=abcdefg&company-b-id=1234567`
5. Now, both Company A and Company B have the audience member's ID from both companies.

The problem with this method is that there is a growing number of ad companies, and these companies partner with lots of other companies.  What seems like a straightforward solution for two companies becomes complex as the number of companies grow.  For example, if Company A partners with 10 different companies, they need to add 10 beacons, one for each company.

For example:



This methodology slows ad traffic substantially
