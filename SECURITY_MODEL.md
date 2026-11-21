# Security model — Bibo Le Robot

_Draft threat model, based only on `PRIVACY_POLICY.md`. When this was written the repository held no application code, so everything below about the app is inferred from the policy, not verified in code. Update it when the app code is added._

## System overview and trust boundaries
Bibo is a companion-robot app for children aged 3–6, distributed on Google Play (Designed for Families). From the policy:
- Voice interaction through the device microphone (mini-games, simple word recognition), described as local processing.
- A parental gate protecting advanced settings.
- No ads, no advertising identifiers, no collection of personal data; support contact `support@biborobot.com`.

Trust boundaries (expected, unverified): child user ↔ app UI; app ↔ device microphone/OS permissions; parent ↔ parental gate; app ↔ any third-party SDKs or speech services.

## Components
| Name | Covers |
|---|---|
| Privacy policy | `PRIVACY_POLICY.md` |
| Mobile app | Not in the repository yet |
| Voice / microphone | Not in the repository yet |
| Parental gate | Not in the repository yet |

## Entry points and who can reach them
- The app UI, used by young children (no login described in the policy).
- Microphone input.
- Parental-gate-protected settings.
- No server-side entry points are described.

## Assets and data sensitivity
- Children's voice audio (highly sensitive under COPPA/GDPR).
- Any device or usage identifiers (policy claims none collected).
- Compliance posture: the accuracy of the privacy policy's claims against the actual app behaviour.

## Attacker profiles
- A curious child bypassing the parental gate.
- Third-party SDKs collecting data contrary to the policy.
- Not yet confirmed by the maintainers which attackers matter.

## Existing controls (claimed in policy)
- Local-only voice processing, no retention or sale of recordings.
- No advertising identifiers, no ads.
- Parental gate on advanced settings.

## Out of scope / accepted risk
- None stated yet.

## Open questions
- Does voice processing truly stay on the device, or does any audio reach a cloud speech service?
- Are there any backend services, analytics, or crash-reporting SDKs?
