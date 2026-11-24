# XY Social App — Expo + React Native starter

A black-and-purple social app starter for Android and iOS. It includes Expo Router navigation, email/password authentication, phone OTP authentication hooks, a home feed, media picker, profile screen, and a starter Supabase schema.

## Requirements
- Node.js LTS
- Expo Go on a test phone, or Android Studio / Xcode for native builds
- A Supabase project

## Run locally
1. Extract this ZIP.
2. In the project folder run `npm install`.
3. Copy `.env.example` to `.env`.
4. Fill in your Supabase Project URL and anon/publishable key.
5. Run `npx expo start`.
6. Scan the QR code with Expo Go, or press `a` for Android / `i` for iOS simulator.

Never put a Supabase `service_role` key in a mobile app. Only use the anon/publishable key in the app.

## Supabase setup
1. Create a Supabase project.
2. Open SQL Editor and run `supabase/schema.sql`.
3. In Authentication settings, enable Email. Configure email confirmation and password rules.
4. To use phone login, enable Phone provider and configure an SMS provider in Supabase. Phone OTP may incur provider charges.
5. Create `.env` from `.env.example` with:
   - `EXPO_PUBLIC_SUPABASE_URL`
   - `EXPO_PUBLIC_SUPABASE_ANON_KEY`
6. Restart Expo after editing `.env`.

## Important starter limitations
- This is a starter project, not a deployed or store-ready social network.
- Email and phone are two sign-in methods. Account linking between an existing email account and phone number needs a deliberate account-linking flow before launch.
- The create screen uploads image/video files to a private bucket, but feed media rendering with signed URLs needs to be added before launch.
- Stories table exists, but story creation/viewer UI is not implemented yet.
- Short-video playback/feed, comments UI, likes persistence, follows UI, search, chat, push notifications, admin moderation dashboard, age assurance, deletion/export tools, and abuse-rate limiting remain future work.
- The starter feed currently queries public posts. Extend its RLS policies before enabling follower-only/private posts.
- The current profile policy is intentionally basic; review data exposure and all RLS policies with a qualified developer before launch.
- Do not launch publicly until you have moderation workflows, report review, privacy policy, terms, child-safety protections, and security testing.

## Suggested next milestones
1. Complete signed media URL rendering and profile editing.
2. Implement likes/comments/follows with RLS-safe queries.
3. Implement stories and short-video playback.
4. Add safe messaging only after block/report and message controls are complete.
5. Add moderation queue, content controls, account deletion and privacy/export flows.
6. Test on real Android and iOS devices, then prepare store listings.

## App identifiers
Replace `com.example.xy` in `app.json` with an identifier you own before publishing.
