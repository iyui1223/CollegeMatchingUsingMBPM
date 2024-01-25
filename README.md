# CollegeMatchingUsingMBPM

A college matching using maximum bi-partite matching(MBPM).
While the core of algorithm inheriting the MBPM, it introduces a priority, 
so that most-highly prioritized candidate can get the most prefered posts (if it also satisfy to optimize the preferences of equally ranked candidates).

This algorithm assumes the usage for satisfuction optimization at a collegious university at which candidates 
who were successfully qualified but not found a place at the first choice college is "pooled" and picked from other colleges.

It also improve the job-satisfaction at a company which employs "Japanese job rotating system" in which every few years
the employees are transfered to do different jobs within the company, sometimes regardless to their own preference nor to the offices who got alocated completely unqualified employees.

This algorithm prioritize the preference of "top-performing" candidates and may neglects the least performing ones.

1. The candidates provide yes-no preferences for each posts as boolean matrix, and post-holders do vice versa (just as in MBPM).
2. Candidates are also ranked by their performance or qualification.  The more minutely the ranks are provided, the more the upper ranked candidates are prioritized.
3. Among the "yes" n posts, candidates are asked to set the priority of posts from 1-nth ranks. Candidates can set multiple posts in the same priority order.
( Number of ranks for both candidates and posts has to be nearly the same )
5. MBPM loop starts using from more prioritized candidates/posts sets.
   
   a. BPM is performed only using the 1st-rank candidates and with their top 1 prefered posts are set as "true" in boolean matrix. Remove the matched candidats/posts from mother matrix.

   b. BPM is performed only using the remaining 1st-rank candidates with their top 1-2 prefered posts.  Remove the matched candidats/posts from mother matrix.
   
   c. BPM is performed only using the 2nd-rank and pooled candidates with their top 1-2 prefered posts.  Remove the matched candidats/posts from mother matrix.
   
   d. BPM is performed only using the pooled candidates with their top 1-3 prefered posts.  Remove the matched candidats/posts from mother matrix.
   
   e. BPM is performed only using the 3rd-rank and pooled candidates with their top 1-3 prefered posts.  Remove the matched candidats/posts from mother matrix.
   
   ...
   
   f. Last remaining candidates are then matched with last remaining jobs using BPM.  
   


