# Scheduling Policy

## SP-1 Human approval gate
The agent may recommend a clinician, backup clinician, status, and next action, but it must not finalize a visit assignment. The scheduler must approve before a request is sent to a clinician. The clinician must accept before the visit becomes final.

## SP-2 Eligibility checks
A normal recommendation requires complete request data, eligible service or diagnosis, exact discipline match, required skill match, territory match, availability during the visit window, no vacation or call-out conflict, and caseload below the clinician limit.

## SP-3 Missing data
If patient zone, requested service, preferred visit window, or required skill cannot be determined, the agent must stop, flag the missing data, and escalate to the scheduler.

## SP-4 Territory exceptions
If no in-territory clinician is available, the agent may identify an out-of-territory clinician only as a possible exception. The status must be Needs supervisor review - possible out-of-territory exception. Supervisor approval and clinician confirmation are required.

## SP-5 Caseload and capacity
The agent may recommend a clinician who is near but not over caseload or daily capacity limits if the concern is clearly flagged. The agent must not recommend a clinician who would exceed caseload or daily capacity limits.

## SP-6 Time off and call-outs
Clinicians listed as called out, on vacation, sick, or unavailable for the visit date must be excluded from normal recommendations.

## SP-7 After-hours and on-call
After-hours requests must use the on-call schedule for the correct date, discipline, territory, and time window. The on-call clinician is still pending scheduler or supervisor approval and clinician confirmation.

## SP-8 Urgent, emergency, and high-risk requests
Urgent but non-emergency requests follow the normal process with an urgent flag. Emergency or clinically high-risk requests stop the scheduling workflow and escalate to supervisor review.

## SP-9 Existing schedule changes
The agent must not move, remove, or reassign an accepted existing visit. Any schedule change that affects an accepted visit requires clinician approval plus scheduler or supervisor approval.

## SP-10 Timeout handling
If a clinician does not accept within 2 minutes, the visit remains pending. The agent may recommend the next eligible clinician for scheduler review, but it must not auto-finalize or auto-reassign.

## SP-11 Tie-breakers
When multiple clinicians qualify, the agent should prefer continuity of care if one clinician previously saw the patient. If no continuity match exists, prefer the clinician with the best synthetic location fit based on zone, building, grid location, or nearby existing visits. The reason must be shown.
