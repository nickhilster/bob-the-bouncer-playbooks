# Playbook Schema (v1)

One YAML file per scam per country: `playbooks/<cc>/<scam-id>.yaml`.

```yaml
id: digital-arrest            # slug, unique within country
country: IN                   # ISO 3166-1 alpha-2
country_name: India
name: "Digital Arrest"         # common name
status: verified              # verified | draft | emerging
channels:                     # where it reaches the victim
  - phone
  - video-call
  - whatsapp
first_seen: "2023"            # year the pattern emerged (sourced)
scale:                        # sourced figures only, with source
  text: "123,000+ cases reported in 2024; ~₹2,000 crore lost"
  source: "https://nyaaya.org/nyaaya-weekly/digital-arrest-how-to-spot-the-scam-and-protect-your-savings/"
hook: "A parcel in your name was seized — drugs found."   # the opening
script:                       # beats, in order
  - "Courier/customs call or WhatsApp: illegal substances in your parcel."
  - "Handoff to a 'CBI/ED/police officer' on video call, in uniform."
  - "Fake arrest warrant shown on screen."
  - "'Digital arrest' declared."
  - "Isolation: stay on camera, tell no one — not family, not a lawyer. Hours, sometimes days."
  - "Demands a 'verification' transfer (UPI, crypto). Promises it will be returned."
kill_shot: "There is no such thing as 'digital arrest' in Indian law. Real police never arrest anyone over a video call."
kill_shot_local:             # the kill-shot in the victim's language
  hi: "डिजिटल अरेस्ट नाम की कोई चीज़ भारतीय कानून में है ही नहीं। असली पुलिस वीडियो कॉल पर कभी गिरफ़्तार नहीं करती।"
  mr: "'डिजिटल अरेस्ट' नावाची कोणतीही गोष्ट भारतीय कायद्यात नाही. खरी पोलीस व्हिडिओ कॉलवर कधीही अटक करत नाही."
safe_path:                    # what the victim should do, in order
  - "Hang up. Hanging up is always safe."
  - "Tell your family immediately — the exact opposite of the scammer's order."
  - "Call 1930, the national cybercrime helpline."
  - "Report at cybercrime.gov.in."
  - "If money moved, call your bank immediately."
helplines:
  - name: "National Cybercrime Helpline"
    number: "1930"
  - name: "Report online"
    url: "https://cybercrime.gov.in"
sources:                      # every factual claim traceable
  - "https://www.canada.ca/en/revenue-agency/corporate/scams-fraud/recognize-scam.html"
notes: "Free text: context, variants, what's contested."
```

## Field rules

1. **One scam, one file.** Variants go in `notes`, not new files, unless the script genuinely differs.
2. **Kill-shot first.** If you can't write the one sentence that kills it, the playbook isn't ready.
3. **Local language is not optional.** `kill_shot_local` must cover the country's major victim languages before `status: verified`.
4. **Helplines are verified, not remembered.** Check the number against an official source before committing.
5. **No victim-blaming, ever.** The playbook describes the *scammer's* mechanics, never the victim's failings.
