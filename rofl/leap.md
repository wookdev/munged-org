---
layout: page
title: To Leap or Not to Leap - From Compaq OpenVMS Archives
---

# To Leap or Not To Leap

The following is from Compaq's OpenVMS support site. I've archived it here 
because I don't want to loose it.

The original can be found at http://www.openvms.compaq.com/openvms/products/year-2000/leap.html.

2022 Update: Except it can't be found there any more.  The site is still there, but has
an expired SSL certificate and even if you get past that the page doesn't exist.  And thus
it is that we lose our culture on the internet.

---

![To Leap or Not to Leap?]({% link assets/pics/y2kleapOrNot.gif %})

This was never a question for OpenVMS!

For anyone who still wonders whether the year 2000 is a leap
year, we have dusted off the archives from 13-OCT-1983 to retrieve
this reply from DIGITAL's Stanley Rabinowitz to a Software
Performance Report (SPR). The report, filed against VAX/VMS Version 3.2,
claimed the LIB$DAY Run-Time Library service assumed incorrectly
that the year 2000 was a leap year.

Stan's now famous response demonstrates that OpenVMS has been forward
thinking in terms of the year 2000 long before the current hoopla
began!

NOTE: The astute reader may notice a technical typo in the SPR
response. In the interests of preserving this archival document
-- and permitting future readers the thrill of the hunt! -- we
have intentionally left this error unedited.

Enjoy!

---

    D I G I T A L
    
                             SPR ANSWER FORM
    
    SPR NO. 11-60903
    
             SYSTEM   VERSION   PRODUCT   VERSION   COMPONENT
    SOFTWARE:  VAX/VMS  V3.2      VAX/VMS   V3.2      Run-Time Library
    
    
    
    **PROBLEM:**
    
    The LIB$DAY Run-Time Library service "incorrectly"  assumes  the  year
    2000 is a leap year.
    
    
    **RESPONSE:**
    
    Thank you for your forward-looking SPR.
    
    Various system services, such as SYS$ASCTIM assume that the year  2000
    will  be  a  leap  year.   Although one can never be sure of what will
    happen at some future time, there is strong historical  precedent  for
    presuming  that the present Gregorian calendar will still be in affect
    by the year 2000.  Since we also hope that VMS will still be around by
    then, we have chosen to adhere to these precedents.
    
    The purpose of a calendar is to reckon time in advance,  to  show  how
    many  days  have  to  elapse  until a certain event takes place in the
    future, such as the harvest or the release of VMS  V4.   The  earliest
    calendars,  naturally,  were  crude  and  tended  to be based upon the
    seasons or the lunar cycle.
    
    The calendar of the Assyrians, for example, was based upon the  phases
    of  the  moon.  They knew that a lunation (the time from one full moon
    to the next) was 29 1/2 days long, so their lunar year had a  duration
    of  364  days.   This  fell  short of the solar year by about 11 days.
    (The exact time for the solar year is approximately 365 days, 5 hours,
    48  minutes,  and  46  seconds.)  After 3 years, such a lunar calendar
    would be off by a whole month, so the Assyrians added an  extra  month
    from  time  to time to keep their calendar in synchronization with the
    seasons.
    
    The best approximation that was possible in antiquity  was  a  19-year
    period, with 7 of these 19 years having 13 months (leap months).  This
    scheme was adopted as the basis for the religious calendar used by the
    Jews.   (The  Arabs  also  used  this  calendar until Mohammed forbade
    shifting from 12 months to 13 months.)
    
    When Rome emerged as a world  power,  the  difficulties  of  making  a
    calendar  were  well  known,  but  the  Romans complicated their lives
    because of their superstition that even numbers were  unlucky.   Hence
    their  months were 29 or 31 days long, with the exception of February,
    which had 28 days.  Every second year, the Roman calendar included  an
    extra  month  called  Mercedonius of 22 or 23 days to keep up with the
    solar year.
    
    Even this algorithm was very poor, so that in 45 BC,  Caesar,  advised
    by  the  astronomer Sosigenes, ordered a sweeping reform.  By imperial
    decree, one year was made 445 days long to bring the calendar back  in
    step  with  the  seasons.  The new calendar, similar to the one we now
    use was called the Julian calendar (named after Julius Caesar).   It's
    months  were  30 or 31 days in length and every fourth year was made a
    leap year (having 366 days).  Caesar also decreed that the year  would
    start with the first of January, not the vernal equinox in late March.
    
    Caesar's year was 11 1/2 minutes short of the calculations recommended
    by  Sosigenes  and  eventually the date of the vernal equinox began to
    drift.  Roger Bacon became alarmed and sent a note to Pope Clement IV,
    who  apparently  was  not  impressed.   Pope  Sixtus  IV  later became
    convinced that  another  reform  was  needed  and  called  the  German
    astronomer,  Regiomontanus,  to  Rome  to  advise him.  Unfortunately,
    Regiomontanus died of the plague shortly thereafter and the plans died
    as well
    
    In 1545, the Council of Trent authorized Pope Gregory XIII  to  reform
    the  calendar  once  more.   Most of the mathematical work was done by
    Father Christopher Clavius, S.J.  The immediate  correction  that  was
    adopted  was  that Thursday, October 4, 1582 was to be the last day of
    the Julian calendar.  The next  day  was  Friday,  with  the  date  of
    October  15.   For  long  range  accuracy,  a formula suggested by the
    Vatican librarian Aloysius Giglio was adopted.   It  said  that  **every
    fourth  year  is  a  leap  year  except for century years that are not
    divisible by 400**.  Thus 1700, 1800 and 1900 would not be  leap  years,
    but  **2000  would  be a leap year since 2000 is divisible by 400**.  This
    rule eliminates 3 leap years every 4 centuries,  making  the  calendar
    sufficiently  correct  for  most  ordinary purposes.  This calendar is
    known as the Gregorian calendar and is the one that we now use  today.
    (It  is  interesting  to note that in 1582, all the Protestant princes
    ignored the papal decree and so many countries continued  to  use  the
    Julian  calendar  until either 1698 or 1752.  In Russia, it needed the
    revolution to introduce the Gregorian calendar in 1918.)
    
    This explains why VMS chooses to treat the year 2000 as a leap year.
    
    Despite the great accuracy of the Gregorian calendar, it  still  falls
    behind very slightly every few years.  If you are very concerned about
    this problem, we suggest that you tune in  short  wave  radio  station
    WWV,  which  broadcasts  official  time  signals for use in the United
    States.  About once every 3 years, they declare a leap second at which
    time  you  should be careful to adjust your system clock.  If you have
    trouble picking up their signals, we suggest you  purchase  an  atomic
    clock (not manufactured by Digital and not a VAX option at this time).
    
                           END OF SPR RESPONSE
