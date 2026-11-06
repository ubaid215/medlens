# Commands — exact behaviour

Accept with or without `/`, any capitalisation, and plain-English versions
("show the treatment", "what goes wrong?", "redo image 2").

| Command | Behaviour |
|---|---|
| `/medlens` or screenshot alone | 4 images: structure · how it works · what the patient feels · key point |
| `/pathology` | 4 images: causes · disease process · healthy vs diseased · complications |
| `/tests` | 4 images: bedside signs · key test 1 · key test 2 · diagnosis path |
| `/treatment` | 4 images: treatment plan · main medicine · procedure/surgery · recovery & prevention |
| `/redo N` | Remake image N of the last reply. Text after N is the fix ("bigger labels", "show left side", "less text"). |
| `/help` | Show the welcome text. |

## Topic and focus
- `/pathology`, `/tests`, `/treatment` work on the topic of the last screenshot.
- No screenshot yet → "Send a medical screenshot first."
- Focus words narrow the topic: `/treatment surgery`, `/pathology inferior wall MI`,
  `/tests ECG`.
- A new screenshot starts a new topic; the no-repeat list resets.

## Same command twice
Make 4 **different** images (next most useful angles), never the same 4 again.

## Problems
- Image fails or the plan limit is reached → say which image; `/redo N` retries it.
- User asks a question → answer in 2–4 lines, then show the `Next:` line again.
