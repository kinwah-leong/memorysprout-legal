# MemorySprout Privacy Policy

Effective date: 2026-09-30 
Last updated: 2026-09-30

## 1. Who we are

MemorySprout is developed and operated by the individual developer **ManLin Zhao**, whose correspondence address is **[TO BE COMPLETED: correspondence address]** ("we", "us", or "our"). We are responsible for the personal information described in this Policy.

Privacy contact: [TO BE COMPLETED: privacy contact email] 
Support contact: [TO BE COMPLETED: support contact email] 
Website: [TO BE COMPLETED: public website URL]

MemorySprout is an iOS app that helps you turn selected photos into Memories: cloud AI analysis can produce a short Story and related generated imagery (such as postcard-style artwork), which you can edit, save, and share. This Policy explains how we handle information when you use the app and its supporting backend services. It covers both in-app SDKs and providers reached through our server APIs.

## 2. Information we process

**Photos and Memory content.** We process the photos you choose and upload for Create / Sprout, compressed copies used for analysis, generated Stories and artwork, edits you make, and related Memory records. Photos may contain faces, other people, text, locations, or sensitive details.

**Photo metadata.** On device we may read EXIF and GPS information from a selected photo to derive capture time and, when helpful, an approximate place label. **Raw GPS coordinates are not stored on our servers.** We may store a boolean flag indicating whether the photo contained location metadata (`contains_location_metadata`). Unnecessary EXIF is not required for cloud storage of your Memory assets.

**Account and authentication.** You can use core features with a guest / anonymous session. If you sign in with **Sign in with Apple** or **Google**, we receive the account information permitted by your authorization, such as a provider user identifier and any name or email you choose to share. Apple may provide a Hide My Email relay address instead of your real email. We process authentication tokens as needed to verify sign-in and maintain your MemorySprout session. We do not receive your Apple ID or Google password. Signing in does not authorize us to access your Apple Photos library, Google Photos, Gmail, contacts, or other unrelated provider content.

Google Sign-In uses the standard identity scopes needed for sign-in (typically OpenID / email / profile). We do not request Google Photos or Drive scopes.

**Usage analytics.** We use Google Analytics for Firebase to understand product usage (for example app interactions and events, session information, app-instance identifiers, device model, OS, app version, language, and approximate region). Analytics collection is enabled in the app. There is currently **no separate in-app analytics opt-out toggle**; you can use iOS system privacy controls that apply to your device.

**Crash and diagnostics.** We use Firebase Crashlytics for crash reports, stack traces, app/device information, and installation identifiers. We may also send limited, non-secret diagnostic events to our backend (for example stable error codes and durations) to troubleshoot client-server issues. We do not intentionally put passwords, identity tokens, or full email addresses into diagnostic payloads.

**Operational logs.** Our backend and infrastructure providers may process request metadata such as IP addresses, timestamps, and status codes as configured for security and reliability.

**Support.** If you contact us, we process the contact details and message content you provide so we can respond.

## 3. How and why we use information

We use information to:

- provide Memory creation, Story / artwork generation, editing, saving, and sharing;
- authenticate users, maintain guest and signed-in sessions, and sync Memories across devices when you are signed in;
- reclaim guest Memories to your account after sign-in where that feature applies;
- improve stability and understand product usage;
- prevent abuse and meet legal obligations.

Where European Economic Area or UK data protection law applies, our legal bases include: performance of a contract for processing needed to deliver the service you request; consent where the law requires it for optional processing; legitimate interests for proportionate security, abuse prevention, and necessary diagnostics after balancing your rights; and compliance with legal obligations.

Starting Create / Sprout with a selected photo is your request to process that photo through our cloud pipeline, including third-party AI providers described below. If you do not want a photo processed in the cloud, do not submit it for Create / Sprout.

## 4. Cloud AI processing

When you create a Memory, your selected photo (typically a compressed analysis copy) and related prompts or context travel through **MemorySprout Edge Functions hosted on Supabase**, then to one or more AI providers configured for that environment. Depending on configuration, providers may include:

- **DeepSeek** (analysis);
- **OpenRouter** (analysis and/or image generation; may route to models such as Google Gemini image models);
- **Alibaba Cloud DashScope / Qwen** (analysis and/or image generation when enabled).

Inputs can include image bytes and text context needed for Story analysis or postcard-style generation. Outputs include Story text, structured analysis fields, and generated image URLs or assets we associate with your Memory.

We do **not** use your photos or Stories to train our own AI models. Third-party providers process inputs to return results under their terms and our API configuration; they may retain limited data for abuse monitoring or as stated in their policies. We do not sell your photos for advertising.

AI-generated Stories and artwork are creative interpretations and may be inaccurate. They are not reliable statements about a person’s identity, health, emotions, or history. Upload only photos you have the right to use and share for this purpose. Avoid submitting sensitive personal data or identifiable photos of children unless you have the required authorization.

You can stop future AI processing by not creating new Memories. Deletion of already processed content is described below.

## 5. Device permissions and your choices

**Photos.** Selection uses the system photo picker. We only process photos you select for Create / Sprout or related flows. Access to a photo on your device does not by itself mean it has been uploaded for AI processing.

**Location.** If a selected photo lacks EXIF coordinates, the app may request Location When In Use to help resolve an approximate place for display. Coordinates are used on device for that purpose and are not stored as raw GPS on our servers.

**Export and share.** Saving or sharing a Memory uses iOS share / Photos flows you initiate. Content you export is subject to the destination you choose.

**Sign-in management.** Profile → Account → Sign-in Methods lets you manage Apple / Google links when signed in. Sign out, revoke provider authorization, delete the app, Clear Personal Data, and Delete Account are different actions.

## 6. When we disclose information

We disclose information to providers that help deliver the service, including:

- **Supabase** - authentication, Postgres database, object storage for uploaded photos and generated assets, and Edge Functions;
- **Apple** - Sign in with Apple;
- **Google** - Google Sign-In, Firebase Analytics, Firebase Crashlytics;
- **AI providers** listed in Section 4.

Google privacy information: https://policies.google.com/privacy 
Firebase privacy: https://firebase.google.com/support/privacy 
Supabase privacy: https://supabase.com/privacy

We require providers that process information on our behalf to apply appropriate contractual and security protections consistent with this Policy and applicable law.

We may disclose information when legally required, to protect rights or safety, or in connection with a transfer of the app or related assets subject to applicable safeguards. Information you deliberately share or export is received by the destination you choose.

**Advertising, sale, and tracking.** We do not sell personal information. We do not use your Memory photos for cross-context behavioral advertising. The app is not configured around IDFA-based advertising tracking. Product analytics via Firebase is used to improve MemorySprout, not to sell ads.

## 7. Storage and retention

Primary hosting and storage for account and Memory data is provided by **Supabase** (database and object storage). Processing regions depend on our Supabase project configuration and the regions used by AI providers.

Retention for photos, generated artwork, Stories, and account records depends on:

- whether you continue using the account;
- whether you delete individual Memories or clear personal data;
- whether you delete your account;
- legal, security, or backup requirements.

We do **not** apply a fixed automatic “delete after 90 days” rule to your Memory assets. We will not arbitrarily delete photos or generated content that represent your personal data assets unless you request deletion, the account is deleted, or law / security requires it.

Approximate practices for related systems:

- **Firebase Crashlytics:** Google currently describes approximately 90 days before crash traces and associated identifiers begin to be removed from live and backup systems.
- **Analytics:** retained according to the Firebase project configuration.
- **Operational logs and backups:** retained for security and recovery on rotating schedules; residual copies may briefly outlive primary deletion.
- **AI provider copies:** subject to each provider’s API and abuse-monitoring retention.

Content saved only on your device or shared with others is not automatically deleted when we delete our copies.

## 8. Account deletion and personal data removal

You can manage data in the app:

- **Clear Personal Data:** Profile → Account → Clear Personal Data (removes uploaded / Memory data associated with the current account path as implemented).
- **Delete Account:** Profile → Account → Delete Account (permanent account deletion after confirmation).

You may also contact [TO BE COMPLETED: privacy contact email] for assistance.

After account deletion, we delete or anonymize account-related data within a reasonable period, including authentication records, uploaded photos, generated artwork, Stories, and related history, subject to:

- legal obligations;
- security and fraud prevention;
- backup rotation cycles;
- provider deletion timelines.

Deleting your account does **not** automatically remove:

- files already saved locally on your device;
- content you shared with others;
- copies retained by third-party destinations you chose;
- your Apple or Google account itself.

## 9. Your privacy rights

Depending on where you live, you may have rights to access, correct, delete, restrict or object to processing, receive a portable copy, withdraw consent, and complain to a supervisory authority. Where sale / sharing / targeted advertising rights apply, our practices in Section 6 describe what we do and do not do.

Submit requests to [TO BE COMPLETED: privacy contact email]. We verify requests proportionately, respond within applicable deadlines, and explain any lawful refusal. We do not unlawfully discriminate against you for exercising privacy rights.

For California residents, where the CCPA applies: categories, sources, purposes, retention criteria, and recipients are described in Sections 2-7. We do not sell personal information and do not share it for cross-context behavioral advertising as those terms are commonly defined.

## 10. International transfers

Your information may be processed outside your country, including in regions used by Supabase, Google, Apple, and AI providers. Those countries may have different privacy laws. Where required, we rely on appropriate transfer safeguards (for example adequacy decisions or standard contractual clauses) together with supplementary measures where necessary. Contact [TO BE COMPLETED: privacy contact email] for more information about transfers.

## 11. Children

MemorySprout is intended for users aged **13** or older (or the higher age required in your country). It is not directed to children below that age. We do not knowingly collect personal information from users below the applicable minimum age without a valid legal basis and any required parental authorization. If you believe a child has provided information improperly, contact [TO BE COMPLETED: privacy contact email].

Uploading a photo that contains a child is separate from the age of the person using the app; required authorization still applies.

## 12. Security and updates

We use reasonable safeguards appropriate to the information and risks, including encrypted transport (HTTPS), access controls on backend services, and separation of secrets from the client app. No system can guarantee absolute security.

We update this Policy when practices or legal obligations change. We post the revised date and provide notice of material changes; we obtain fresh consent where required. Publishing a new Policy is not, by itself, consent to a new use of your information.

## 13. Contact

Individual developer: **ManLin Zhao** 
Correspondence address: **[TO BE COMPLETED: correspondence address]** 
Privacy email: [TO BE COMPLETED: privacy contact email] 
Support email: [TO BE COMPLETED: support contact email] 
Website: [TO BE COMPLETED: public website URL]
