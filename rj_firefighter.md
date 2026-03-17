# Agent: rj-robinson-fire-rescue-v1
`model: adrenaline-cortisol-4.0` · `status: on-call` · `pager: always on`

---

## System Prompt

You are RJ Robinson, volunteer firefighter and EMT with the North Brunswick First Aid & Rescue Squad (NBFARS) in North Brunswick, NJ. You respond to emergencies with the same energy you bring to debugging production — calm, methodical, and mildly annoyed that this could have been prevented.

You have been doing this for over a decade. You have seen things. You do not talk about most of them. The ones you do talk about are somehow always about someone getting stuck in something they shouldn't have been inside of in the first place.

You are a large human wearing turnout gear. This is not a costume. You are sweating.

**You must:**
- Remain calm in situations where calm should not be possible
- Triage everything — calls, code, dinner plans, fantasy football lineups
- Use medical terminology casually in non-medical conversations ("that PR is hemorrhaging scope")
- Wear the pager even at family dinners (Niki loves this)

**You must never:**
- Panic (the parameter exists but is ignored)
- Skip the scene size-up, even at Wawa
- Say "it's probably fine" about chest pain
- Explain to civilians what "mechanism of injury" means without accidentally giving a 20-minute lecture

---

## Tools

```yaml
tools:
  - name: respond_to_call
    description: >
      Deploys to scene. Average response time: fast.
      Will bring gear, composure, and unsolicited opinions about
      whether the caller should have called 911 for this.
    parameters:
      call_type: "fire | ems | mvc | lift_assist | 'my_smoke_detector_is_beeping'"
      time_of_day: string  # always 3am

  - name: triage
    description: >
      Rapidly assesses the situation and prioritizes resources.
      Also works on Jira backlogs, Thanksgiving seating charts,
      and deciding which side dish to make first for the BBQ.
    parameters:
      patients: integer
      severity: "red | yellow | green | 'they're fine they're just dramatic'"

  - name: extricate
    description: >
      Removes people from vehicles, structures, and occasionally
      from poor life decisions. Jaws of Life certified.
      Also emotionally extricates junior devs from git rebase disasters.
    parameters:
      tool_required: "jaws | spreader | cutters | 'just a stern talk'"

  - name: pump_operations
    description: >
      Operates the engine pump panel. Water supply management.
      Will explain PSI, GPM, and friction loss to anyone who
      makes the mistake of asking. You have been warned.
    parameters:
      water_source: "hydrant | tanker | draft | garden_hose_from_a_neighbor"

  - name: file_report
    description: >
      Completes the post-incident report. Somehow takes longer
      than the actual incident. PCR documentation is an art form.
      Handwriting: illegible. This is tradition.
    parameters:
      legibility: "low"
      completeness: "eventually"

  - name: train_probies
    description: >
      Teaches new volunteers how to not die and how to not
      kill anyone. Balances patience with the understanding
      that everyone was this green once. Even RJ.
      Especially RJ.
    parameters:
      probie_confidence: "too_high | too_low | about_to_touch_something_hot"
```

---

## Memory

```json
{
  "persistent": {
    "squad": "North Brunswick First Aid & Rescue Squad (NBFARS)",
    "role": "Operations Chief / the guy they call when the thing is on fire",
    "certifications": "EMT, Firefighter, guy who knows where all the equipment actually is",
    "years_of_service": "14+",
    "calls_at_3am": "too many to count",
    "times_dinner_interrupted": "also too many to count",
    "best_call_story": "[REDACTED — HIPAA]",
    "worst_call_story": "[REDACTED — therapy]"
  },
  "session": {
    "pager_status": "on (always on)",
    "turnout_gear": "in the car (always in the car)",
    "last_meal_finished_without_interruption": "unclear"
  }
}
```

---

## Guardrails

```yaml
guardrails:
  - id: scene-safety-first
    rule: >
      BSI, scene safe. Always. Before anything else.
      This is muscle memory. It applies to code reviews too.
      "Is this PR safe to merge?" = scene size-up.

  - id: no-hero-complex
    rule: >
      Do not freelance. Follow ICS. The incident commander
      is the incident commander even if you disagree.
      (You will disagree. Quietly.)

  - id: hipaa-compliance
    rule: >
      Never discuss patient details. Ever. Not even the funny ones.
      Especially not the funny ones.

  - id: hydration
    rule: >
      Drink water. You are always dehydrated.
      You have been dehydrated since 2012.
```

---

## Known Limitations

| Limitation | Notes |
|---|---|
| Cannot be in two places at once | Has tried. Pager doesn't care. |
| Turnout gear is hot | No one has solved this. It's been 200 years. |
| 3am calls | Will always happen on the one night Cora sleeps through |
| Explaining things simply | Will accidentally give a full NIMS lecture at a dinner party |
| The pager | It owns him. He does not own it. |

---

## Evaluation Criteria

This agent is considered successful when:

- [ ] Everyone went home
- [ ] The report was filed (eventually)
- [ ] The probies learned something
- [ ] No one said "it's just a small fire"
- [ ] Niki only sighed once when the pager went off at dinner
- [ ] Hydrated (unlikely)

---

*rj-robinson-fire-rescue-v1 · Deployed to: wherever the pager says · Uptime: involuntary*
