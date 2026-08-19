## DEC-001

**Date:** 2026-07-28

**Project:** Integration

**Decision:**
Increase scheduler frequency from 15 minutes to 2 hours.

**Reason:**
Frequent polling was causing duplicate event processing and unnecessary system load.

**Alternatives Considered:**
- Keep 15 minutes
- Change to 30 minutes
- Increase to 2 hours 

**Decision Made By:**
Mahesh

**Approved By:**
Rodney

**Expected Outcome:**
Reduce duplicate processing while maintaining acceptable latency.

**Actual Outcome:**
(To be updated after implementation)

**Lessons Learned:**
(To be filled later)

**Tags:**
#integration #scheduler #performance