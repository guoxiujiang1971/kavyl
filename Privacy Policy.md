# Privacy Policy

_Last updated: August 30, 2026_

This Privacy Policy explains how Kavyl ("we", "us", or "our") collects, uses, stores, and protects your information when you use the Kavyl mobile application and related services (the "App"). It applies to all users of the App, wherever they are located, with particular attention to the requirements of the General Data Protection Regulation (GDPR) and the Children's Online Privacy Protection Act (COPPA).

By using the App, you agree to the practices described in this Privacy Policy.

---

## 1. Who We Are

Kavyl is a "mood-first" healing companion app. It provides an AI companion for conversation, mood tracking, and gentle well-being features such as breathing exercises, good-night notes, and wellness tools. We are committed to protecting your privacy and to being transparent about how your data is handled.

If you have questions about this policy, contact us at: **kitterive@qq.com** .

---

## 2. Information We Collect

### 2.1 Information You Provide Directly

- **Account information**: If you choose to sign up, we may store your nickname, avatar, country, locale, and onboarding preferences (such as personality and topics you care about). You may sign in with Apple or use the App anonymously without creating an account.
- **Age information**: We verify age to comply with child-safety laws. If you sign in with Apple, we receive an age range (e.g., 0–12, 13–17, 18+). If you do not, we ask for your year of birth. We do not provide the App to anyone under 13, and we reject and do not store data from users who indicate they are under 13.
- **Mood check-ins**: Emojis, intensity ratings, and short notes you log.
- **Memories you add**: Facts and preferences you voluntarily tell us or the AI companion to remember.
- **Messages**: The text of conversations you have with your AI companion, including any images you attach to a message.
- **Safety plan**: Contacts and self-care strategies you choose to store in the app's safety plan feature.
- **Feedback and reports**: Content you submit through report or feedback features.

### 2.2 Information Collected with Your Permission

- **Health data (HealthKit / Apple Health)**: With your permission, Kavyl writes your breathing sessions to Apple Health as Mindfulness minutes. When you ask a health-related question, Kavyl may read a snapshot of your health data (steps, heart rate, sleep, mindfulness minutes, active energy, and recent workouts) so the AI can answer accurately. This snapshot is sent to our servers only for that purpose. You can revoke access at any time in Settings → Health, or in the App under Me → Data & Privacy → Apple Health (HealthKit).
- **Precise location**: When you ask location-based questions (for example, "what's fun nearby"), we may access your device's location to provide relevant results. Your approximate location may be sent to our servers and to the map and weather data providers described in Section 5, only to fulfill your request. You can disable location access at any time in Settings → Privacy → Location Services.
- **Microphone and speech recognition**: If you use voice input, we access your microphone. Speech recognition and text-to-speech are processed on your device by Apple's system services; we do not receive or store your raw audio.
- **Photo library**: If you choose to save generated or received images, or to upload an avatar, we may add images to or read from your photo library. Saved images may be uploaded to our storage to display them across your devices.

### 2.3 Information Collected Automatically

- **Device and usage information**: Device model, operating system version, app version, and basic diagnostic data needed to keep the service working.
- **Subscription and purchase records**: In-app purchase transactions and subscription status, processed through Apple's App Store.
- **Push notification tokens**: We store a device token so we can deliver notifications you have enabled (such as character greetings and mood reminders).

### 2.4 Information We Do Not Collect

- We do **not** serve advertising and do not use your data for third-party ad targeting.
- We do not sell your personal information.
- We do not require a phone number or email address to start using the App.
- We do not collect health or location data unless you grant permission and actively use the features that require it (see Section 2.2).

---

## 3. How We Use Your Information

We use your information to:

- Provide, maintain, and improve the App and its features;
- Power your AI companion, including generating replies and providing long-term memory so it can recall things you have shared;
- Generate mood reports and summaries of your emotional patterns;
- Deliver personalized features such as good-night notes, greeting cards, and reminders;
- Answer your health- and location-related questions using the data described in Section 2.2;
- Verify your age and protect children from using the App;
- Detect and respond to content-safety issues, including crisis situations where we direct you to appropriate mental-health resources;
- Process subscriptions and purchases through Apple's App Store;
- Deliver push notifications you have enabled;
- Ensure security, prevent abuse, and comply with legal obligations;
- Respond to your support and data-request inquiries.

---

## 4. How the AI Companion Works

To generate a reply, the App builds a prompt that includes your most recent message, recent conversation history, memories the companion keeps about you, and (only when relevant) device context such as your location or a health snapshot. That prompt is processed as follows:

- **Cloud processing (default, when you are online)**: Chat requests are sent to our own server proxy (a Supabase Edge Function), which forwards them to a third-party LLM API provider to generate the reply. This means your message, recent conversation context, selected memories, and (where relevant) location or health snapshot may be transmitted to that provider. We do not use this data for advertising or sell it.
- **On-device processing**: In "Offline-only" mode (Me → Data & Privacy → Offline-only), no chat request leaves your device. Replies are generated on your device using Apple Foundation Models.
- **Speech recognition and text-to-speech** use your device's system capabilities and are processed on-device.
- **Image generation** uses Apple's on-device capabilities where available.

We do not use your conversations to train our own models, and we do not sell your conversations or personal data to any third party.

---

## 5. Storage, Sync, and Third-Party Services

To support features such as long-term memory, cross-device sync, and push notifications, some data is synchronized to our cloud infrastructure:

- **Supabase**: We use Supabase (a hosted backend service) to store data in encrypted databases, handle authentication, run server-side functions, and deliver push notifications. Supabase processes your data on our behalf under our instructions.
- **Third-party LLM provider**: When you use the App online, chat requests are routed through our server proxy to a third-party large-language-model API provider (routed via OpenRouter, e.g. OpenAI models). This provider receives the prompt described in Section 4 solely to generate your reply.
- **Open-Meteo**: When you ask weather-related questions, we may send your approximate location to Open-Meteo to retrieve a forecast.
- **OpenStreetMap (Overpass)**: When you ask for nearby places, we may send your approximate location to OpenStreetMap to retrieve nearby point-of-interest results.
- **Apple**: Purchases and subscriptions are processed by Apple. Sign in with Apple shares only the information you authorize. On-device and offline features rely on Apple's system models. Apple's own privacy practices apply to your Apple ID and payment information.

All data transmitted between the App and our servers is protected with HTTPS encryption. Sensitive fields are encrypted at rest. We review and require that our service providers maintain appropriate security safeguards and comply with applicable privacy law.

---

## 6. Security

We take reasonable technical and organizational measures to protect your data, including encryption in transit (HTTPS), encryption of sensitive fields at rest, and access controls on our systems. No method of transmission or storage is completely secure; while we strive to protect your information, we cannot guarantee its absolute security.

---

## 7. Retention

We retain personal information only as long as necessary to provide the App and its features, comply with legal obligations, resolve disputes, and enforce our agreements. Conversations, mood logs, and memories are retained while your account is active. You may delete your data or account at any time (see Section 9), after which we delete or anonymize your information in accordance with applicable law, subject to legal retention requirements.

---

## 8. Children's Privacy and Age Gating

- The App is **rated 17+** and is intended for young adults and adults. It is **not directed to children under 13**, and we do not knowingly collect personal information from children under 13.
- We verify age at sign-up. If age verification indicates the user is under 13, the account is rejected and no personal data is stored. If a user indicates they are under 13 at any point, we will stop collecting their data and take steps to delete existing data.
- If you believe we have inadvertently collected personal information from a child under 13, contact us at the address in Section 12 and we will promptly delete it.

---

## 9. Your Rights

Depending on where you live (and in particular if you are in the EEA, UK, or another region with similar rights), you have the right to:

- **Access** your personal data;
- **Correct** inaccurate data;
- **Delete** your data and your account;
- **Export** your data in a portable, machine-readable format;
- **Object to or restrict** certain processing;
- **Withdraw consent** at any time where processing is based on consent;
- **Lodge a complaint** with a supervisory authority.

**How to exercise your rights:**

- **In the App**: You can view, edit, and delete the memories the AI companion keeps about you at any time. You can export your data and delete your account directly in the App (Me → Data & Privacy → Export My Data / Delete Account & Data). Deleting your account removes your personal data from our services.
- **By contact**: You may also contact us at the address in Section 12. We will respond within 30 days or as required by applicable law.

We do not sell your personal information, and we do not use your data for automated decision-making that produces legal or similarly significant effects on you, beyond the personalized conversation and mood features described in this policy.

---

## 10. Crisis Intervention and AI Transparency

- The App may detect language indicating emotional distress or self-harm. In such cases, we may provide supportive messages and direct you to locally relevant mental-health crisis resources (e.g., 988 in the US, 116 123 in the UK/Europe). This is a safety feature; crisis-language detection may be processed on-device.
- The AI companion is **not a human**, is not a licensed therapist or medical professional, and does not provide medical, psychological, or crisis treatment. If you are in crisis, please contact a qualified professional or emergency services immediately.

---

## 11. International Data Transfers

Your data may be processed in and transferred to countries other than the one in which you reside, including the United States and other countries where we or our service providers are located (for example, our LLM provider and backend infrastructure). When we transfer personal data from the EEA/UK, we rely on appropriate safeguards (such as the EU Standard Contractual Clauses or equivalent mechanisms) and applicable legal frameworks.

---

## 12. Contact Us

For any privacy questions, requests, or concerns:

- Email: **kitterive@qq.com** 
- Support page: [Kavyl Support](https://github.com/guoxiujiang1971/kavyl/blob/main/SUPPORT.md)
- We aim to respond to all legitimate requests within 30 days.

---

## 13. Changes to This Policy

We may update this Privacy Policy from time to time. When we make material changes, we will notify you through the App or by other appropriate means and update the "Last updated" date at the top of this policy. Your continued use of the App after changes take effect constitutes acceptance of the revised policy.

---

## 14. Governing Law

This Privacy Policy is governed by the laws applicable to our operations, without regard to conflict-of-law principles. If any provision of this policy is found to be invalid or unenforceable, the remaining provisions remain in effect.
