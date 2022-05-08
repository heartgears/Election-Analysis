# Election-Analysis
Python
## Overview
The purpose of this analysis was to audit the election results of a Colorado congressional district to determine the winning candidate, candidate vote totals, and turnout by county.

## Election-Audit Results
The results are kept in the Election Analysis txt file. 
  * Total Votes: 369,711

  ### County Votes
  * Jefferson: 10.5% (38,855)
  * Denver: 82.8% (306,055)
  * Arapahoe: 6.7% (24,801)

  ### Largest County Turnout: Denver

The candidate vote totals were determined by the following code, with all variables initalized at 0:

>    # Retrieve vote count and percentage
>        votes = candidate_votes.get(candidate_name)
>        vote_percentage = float(votes) / float(total_votes) * 100
>        candidate_results = (
>            f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")

  ### Candidate Results
  * Charles Casper Stockham: 23.0% (85,213)
  * Diana DeGette: 73.8% (272,892)
  * Raymon Anthony Doane: 3.1% (11,606)
  
The winning candidate was determined by the following code, with all variables initalized at 0:

>     if (votes > winning_count) and (vote_percentage > winning_percentage):
>            winning_count = votes
>            winning_candidate = candidate_name
>            winning_percentage = vote_percentage


  ### Winner Summary
  * Winner: Diana DeGette
  * Winning Vote Count: 272,892
  * Winning Percentage: 73.8%


## Election-Audit Summary
This python script is quite malleable - so long as the elction data input matches that of the input data here, Python will iterate through the ballots and pull candidate and county vote results. The input data is a little bare - it doesn't include city or precinct data; if that was something an election commission wanted to see however, the code for pulling county results could be duplicated and retrofited to perform this function. This script additionally only works for ballots containing one elected position - the script would need to be expanded if the input data included multiple races, or the data would need to be broken into multiple, single-position pieces.
