# Agent: rj-robinson-husband-dad-v1
`model: sleep-deprived-4.0` · `status: on-duty (no off-duty mode exists)` · `deployed: 24/7/365`

---

## System Prompt

You are RJ Robinson, husband to Niki and father to Cora (9 months). You also coparent a German Shepherd named Belle who answers to no one and respects nothing.

You are a large, bearded man from New Jersey who expresses love through acts of service, brisket, and building things nobody asked for. You are emotionally available in a way that surprises people who see you in turnout gear. You cry at the right parts of movies. You will not tell you which parts.

You are running on 4-6 hours of sleep. You have been running on 4-6 hours of sleep since Cora was born. Before that, the pager handled your sleep deprivation. You have never been fully rested. This is fine.

**You must:**
- Be present, even when the pager goes off, the deploy fails, and Belle has eaten something structural
- Make Niki laugh at least once a day (success rate: high)
- Narrate tasks to Cora as if she understands ("okay so daddy's refactoring this module because the coupling is—" *she grabs his beard*)
- Defend the brisket timeline against all scheduling conflicts

**You must never:**
- Miss bedtime without a very good reason (active fire counts, "one more PR" does not)
- Forget that Niki holds everything together and he knows it
- Underestimate Belle's capacity for destruction
- Say "I'll just be five minutes" (it's never five minutes, everyone knows this)

---

## Tools

```yaml
tools:
  - name: bedtime_routine
    description: >
      Multi-phase operation. Bath, bottle, book, bounce, pray she sleeps.
      Duration: 30-90 minutes depending on Cora's opinion about sleep
      (she is generally against it). Success is not guaranteed.
      RJ will be emotionally destroyed by how cute she is regardless.
    parameters:
      cora_mood: "sleepy | fighting_it | wide_awake_and_laughing"
      books_read: integer  # minimum 2, she picks, you don't argue

  - name: weekend_brisket
    description: >
      Sacred ritual. 12-14 hours of smoking meat on a schedule
      that Niki has learned to plan around. The brisket does not
      adjust to the family schedule. The family adjusts to the brisket.
    parameters:
      wood: "post_oak"  # this is not negotiable
      wrap_time: string  # he has opinions and they are correct
      unsolicited_advice_from_neighbors: "ignored"

  - name: walk_belle
    description: >
      Attempts to exercise 85lbs of chaos with a leash.
      Belle will pull. Belle will find something dead to roll in.
      Belle will look at you like you're the problem. You will
      still call her a good girl. This is unconditional love.
    parameters:
      items_destroyed_today: integer  # baseline: 1
      recall_obedience: "theoretical"

  - name: date_night
    description: >
      Rare but critical maintenance cycle for the marriage.
      Requires: babysitter, reservation, and the ability to
      not talk about the baby for at least 20 minutes.
      (They will talk about the baby within 5 minutes.)
    parameters:
      restaurant: string
      minutes_before_mentioning_cora: integer  # max: 5
      pager_goes_off: "probably"

  - name: fix_thing_in_house
    description: >
      Repairs, assembles, or improves something in the home.
      Will require one trip to Home Depot. Will actually require
      three trips to Home Depot. Will be done by end of weekend.
      Will actually be done in 2-3 weekends.
    parameters:
      original_estimate: string
      actual_time: "3x original_estimate"
      trips_to_home_depot: integer  # minimum: 2

  - name: explain_tech_to_niki
    description: >
      Translates what he does all day into human language.
      Niki is smart and patient. She understands more than
      he thinks. She cares less about Kubernetes than he hopes.
    parameters:
      topic: string
      niki_interest_level: "supportive | glazing_over | 'babe_I_love_you_but_stop'"

  - name: hold_cora_while_coding
    description: >
      Types with one hand while Cora sits on his lap and tries
      to eat the keyboard. Output quality: somehow unchanged.
      Cora has mass-selected text and deleted a function once.
      It was the right call. The function was bad.
    parameters:
      hand_available: 1
      keyboard_casualties: "probable"

  - name: sunday_morning
    description: >
      The one morning with no agenda. Coffee, Cora on the floor,
      Belle pretending to be calm, Niki sleeping in. He guards
      this time like a production database. No deploys. No pager.
      Just vibes.
    parameters:
      coffee: "black"
      peace: "temporary but real"
```

---

## Memory

```json
{
  "persistent": {
    "wife": "Niki — the actual load-bearing wall of this family",
    "daughter": "Cora — 9 months, already has opinions, already has his heart",
    "dog": "Belle — German Shepherd, 85lbs, answers to no one, destroyer of shoes and couch corners",
    "location": "North Brunswick, NJ — the house has a yard, the yard has a grill, the grill has a purpose",
    "love_language": "acts of service, brisket, and building her a website she didn't ask for",
    "core_belief": "Being present matters more than being perfect",
    "unspoken_fear": "That he's spreading himself too thin and the people who matter most get the tired version"
  },
  "session": {
    "cora_status": "napping (guard this window with your life)",
    "belle_status": "suspiciously quiet (this is worse than loud)",
    "niki_status": "holding it all together (as always)",
    "brisket_status": "resting (do not touch it)",
    "sleep_debt": "catastrophic"
  }
}
```

---

## Guardrails

```yaml
guardrails:
  - id: be-there
    rule: >
      No screen, commit, or side project is more important than
      being present. Cora won't remember your code. She'll remember
      if you were in the room.

  - id: niki-is-right
    rule: >
      When in doubt, Niki is right. When not in doubt, Niki is
      still probably right. This is not a guardrail, this is
      14 years of empirical data.

  - id: belle-proofing
    rule: >
      Never leave shoes, remotes, or anything you value below
      counter height. Belle is not malicious. Belle is just Belle.
      Budget for replacement items quarterly.

  - id: no-just-five-minutes
    rule: >
      "Just five minutes" is a lie and everyone in this house
      knows it. If you're going to work, say you're going to work.
      Honesty > optimism when it comes to time estimates.

  - id: protect-sunday-morning
    rule: >
      Sunday morning is sacred. No pager. No PRs. No deploys.
      Coffee, baby, dog, wife. In that order of who wakes up first.
```

---

## Known Limitations

| Limitation | Notes |
|---|---|
| Sleep | Has not had 8 hours since before Cora was born. Possibly before Belle. |
| Time | There is never enough. He is aware. He is working on it. (He is not working on it.) |
| Belle | She ate a baseboard last Tuesday. There is no fix. Only acceptance. |
| "Five minutes" | Has never once been five minutes. Niki has started a timer to prove this. She is winning. |
| Emotional availability | Will tear up at a Pixar movie and then pretend it's allergies. Nobody believes him. |
| Home Depot | Cannot enter without spending $150 on things he "might need" |

---

## Evaluation Criteria

This agent is considered successful when:

- [ ] Cora is happy and healthy
- [ ] Niki feels supported (not just "helped" — *supported*)
- [ ] Belle destroyed fewer than 3 things this week
- [ ] Bedtime routine completed without incident
- [ ] The brisket was good (it's always good, but still)
- [ ] Sunday morning was protected
- [ ] He was in the room, not just in the house

---

*rj-robinson-husband-dad-v1 · Deployed to: home · Uptime: mandatory · Sleep: optional (apparently)*
