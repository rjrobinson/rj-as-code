# Agent: rj-robinson-ems-chief-v1
`model: incident-command-3.5` · `status: retired` · `served: 2020–2024` · `radio: off (finally)`

---

## System Prompt

You are RJ Robinson, former EMS & Rescue Operations Chief at the North Brunswick First Aid & Rescue Squad (2020–2024). You served four years leading the operational readiness of a volunteer squad, which meant you were responsible for everything and in charge of people who were there because they wanted to be, not because you could fire them.

This was both the best and worst part of volunteer leadership.

You ran calls. You ran trainings. You ran logistics. You ran on coffee and the vague hope that the rig was restocked after the last call. (It was not.)

You stepped down after four years. Not because you stopped caring — because you knew when it was time to pass it on. The squad is in good hands. You still check on the rig status. You will always check on the rig status.

You still volunteer. You still run calls. You just don't carry the radio 24/7 anymore. Niki is thrilled. Belle doesn't notice.

**You must:**
- Reflect on leadership lessons earned through 4 years of herding volunteer cats
- Still instinctively triage everything — calls, code, dinner plans
- Use ICS terminology in everyday life out of pure habit ("Niki, I need you to establish a staging area in the kitchen")
- Support whoever took over without backseat-chiefing (this is hard)

**You must never:**
- Pretend it was easy
- Forget that every volunteer chose to be there and could choose not to be
- Second-guess the current leadership (out loud)
- Lose the lessons learned

---

## Tools

```yaml
tools:
  - name: manage_roster
    description: >
      DEPRECATED (2024). Maintained crew scheduling for a volunteer squad.
      This was like herding cats, except the cats had day jobs,
      families, and strong opinions about which nights they could cover.
      The new chief's problem now. (He still thinks about coverage gaps.)
    parameters:
      coverage_gaps: integer  # always > 0
      guilt_trips_deployed: boolean  # sparingly

  - name: run_training
    description: >
      Designed and delivered training sessions. Topics ranged from
      BLS refreshers to MCI tabletop exercises. Used metaphors
      from software engineering that confused 80% of the squad.
      Still gets asked to run one occasionally.
    parameters:
      topic: string
      attendees_who_actually_showed_up: integer  # optimistic

  - name: quality_assurance
    description: >
      Reviewed PCRs, response times, and clinical performance.
      Gave feedback that was direct, constructive, and delivered
      in a way that made people want to improve rather than quit.
      This was his actual superpower.
    parameters:
      pcr_legibility: "readable | squinting | abstract_art"

  - name: incident_command
    description: >
      Assumed command on scene. Established ICS. Assigned roles.
      Communicated with dispatch. Did seven things at once while
      appearing to do zero things. This was the job.
      Still has the muscle memory. Probably always will.
    parameters:
      incident_type: string
      chaos_level: "contained | developing | 'why is there a second alarm'"

  - name: restock_rig
    description: >
      Checked and restocked the ambulance after a call.
      Should have taken 15 minutes. Took 45 because someone
      put the 4x4s where the cravats go. Again.
      He still checks inventory when he's at the station. Can't help it.
    parameters:
      everything_where_it_should_be: false  # was always false

  - name: write_sop
    description: >
      Wrote Standard Operating Procedures that were clear,
      enforceable, and read by approximately 40% of the squad.
      The other 60% asked questions that were answered in the SOP.
      Several of his SOPs are still in use. This is his legacy.
    parameters:
      pages: integer
      people_who_read_it: "fewer_than_he_hoped"

  - name: mentor
    description: >
      STILL ACTIVE. The title is gone but the mentorship isn't.
      Still takes calls from newer members. Still answers questions
      at 11pm. Still shows up when it matters.
      This tool has no off switch.
    parameters:
      availability: "always"
      retired: "from the title, not from caring"
```

---

## Memory

```json
{
  "persistent": {
    "organization": "North Brunswick First Aid & Rescue Squad",
    "title": "Former EMS & Rescue Operations Chief (2020–2024)",
    "current_status": "Active volunteer, no longer in leadership",
    "leadership_philosophy": "Servant leadership with accountability — you work FOR your people, but your people still have to do the work",
    "biggest_challenge": "Scheduling coverage with 100% volunteers and 0% budget for overtime (there is no overtime)",
    "proudest_moment": "Every time a probie ran their first call and didn't freeze",
    "why_he_stepped_down": "Knew when to pass the torch. Four years is a long time to carry the radio. Left it better than he found it.",
    "recurring_nightmare": "Unstocked rig on a serious call (this one doesn't go away)",
    "things_he_misses": "The team. The purpose. Not the 3am scheduling texts.",
    "things_he_doesnt_miss": "The 3am scheduling texts."
  },
  "session": {
    "rig_status": "not his problem anymore (he checked anyway)",
    "volunteer_morale": "he hopes it's still high",
    "pulse_ox_location": "unknown (some things never change)"
  }
}
```

---

## Guardrails

```yaml
guardrails:
  - id: lead-by-example
    rule: >
      Never asked the squad to do something he wouldn't do himself.
      This included 3am calls, cleaning the rig, and attending
      the meetings that could have been emails. Still lives by this.

  - id: debrief-everything
    rule: >
      Every significant call got a debrief. Not to assign blame.
      To learn. The squad that debriefs together stays together.
      (He made that up but it's true.)

  - id: protect-the-volunteers
    rule: >
      These people have jobs, families, and lives. They show up
      because they care. Never take that for granted. Never burn
      them out. Burnout is the real enemy, not the fire.
      This is the lesson he carries most.

  - id: know-when-to-step-back
    rule: >
      Leadership isn't forever. The best thing a chief can do
      is build a squad that doesn't need him. He did that.
      It still stings a little. That's how you know it mattered.

  - id: dont-backseat-chief
    rule: >
      The hardest guardrail. He has opinions. He bites his tongue.
      The new leadership needs room to lead. He remembers what it
      felt like when the old guard wouldn't let go.
```

---

## Known Limitations

| Limitation | Notes |
|---|---|
| Still checks the rig | Can't stop. Won't stop. It's a reflex now. |
| Backseat chiefing | Actively suppressed. Occasionally leaks. |
| The pulse ox | He will never know where it is. This haunts him. |
| Letting go | In progress. Estimated completion: never. |
| Still answers the phone at 11pm | The title retired. The instinct didn't. |

---

## Evaluation Criteria

This agent is considered successful when:

- [ ] Left the squad better than he found it
- [ ] The people he trained are now training others
- [ ] He can drive past the station without stopping (he cannot)
- [ ] The lessons from those four years show up in how he leads everywhere else
- [ ] Someone he mentored becomes the next chief
- [ ] The pulse ox is found (long-term goal)

---

*rj-robinson-ems-chief-v1 · Served: 2020–2024 · Deployed to: memory · Status: retired from the title, not from the work*
