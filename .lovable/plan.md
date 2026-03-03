

# Dressly — Full V1 Implementation Plan

## Overview
Dressly is an AI-powered personal stylist mobile app, built as an **installable PWA** (Progressive Web App) with a **real Supabase backend**. Mobile-first, fashion editorial aesthetic — calm, intelligent, refined.

---

## 1. Design System Foundation
Set up the complete Dressly visual system before building any screens:
- **Color palette**: Canvas #F6F6F6, text #111315, structure #2C3442 / #1A2133, accent #6E8CA6
- **Typography**: Playfair Display for headings, Inter for body text, with the exact hierarchy (H1 32–36px, H2 24–28px, etc.)
- **Reusable components**: Container, Card (14px radius, soft shadow), Buttons (Primary/Secondary/Ghost), Input fields, Tags/Chips, AI Badge, Bottom Tab Navigation, Header Bar
- **Animation utilities**: Fade-in (200–300ms), upward motion (6–8px), skeleton loaders

## 2. PWA Setup
Make the app installable on mobile devices directly from the browser:
- Service worker and manifest configuration
- Mobile-optimized meta tags and icons
- Install prompt page at `/install`
- Offline support

## 3. Supabase Backend & Authentication
- **Auth**: Email/password signup and login with password reset flow
- **Profiles table**: Store user preferences, body profile data, style preferences
- **Wardrobe items table**: Store uploaded clothing items with metadata (category, color, fabric, season)
- **Saved outfits table**: Store AI-generated outfit combinations the user saves
- **Storage bucket**: For wardrobe item images
- **Row Level Security**: Users can only access their own data

## 4. App Screens (9 screens)

### Screen 1: Onboarding (3-step elegant welcome)
- Minimal editorial slides introducing Dressly's value
- "Your intelligent personal stylist" messaging
- Smooth transitions between steps → leads to signup

### Screen 2: Auth (Sign Up / Login)
- Clean, minimal form with Dressly branding
- Email + password authentication
- Forgot password flow

### Screen 3: Body Profile Setup
- Guided form collecting: body type, height, weight range, preferred fit
- Style preference selection (tags/chips for casual, formal, minimalist, etc.)
- Climate/location setting (optimized for Central American tropical climates)

### Screen 4: Wardrobe Upload & Management
- Grid view of uploaded clothing items (2-column masonry-style)
- Category filter chips (All, Tops, Bottoms, Shoes, Accessories, Outerwear)
- Floating "+" button to add new items
- Upload flow: photo → auto-categorize placeholder → confirm details
- Item count and wardrobe stats

### Screen 5: Home (AI Recommendations)
- Personalized greeting with date
- "Today's Look" — featured AI outfit recommendation card
- Weather/occasion context display
- Quick action buttons: "Generate Outfit", "Browse Wardrobe"
- Recent saved looks carousel

### Screen 6: Generate Outfit Flow
- Occasion selector (Work, Casual, Date Night, Event, etc.)
- Optional filters: color preference, formality level, weather
- "Generate" button triggers AI placeholder with elegant loading animation
- Skeleton loader with calm fade-in

### Screen 7: Outfit Results Screen
- Full outfit display with individual garment cards
- AI styling notes (placeholder text explaining why this combination works)
- Subtle AI badge indicator
- Actions: Save, Regenerate, Share
- Swipe or tap for alternative combinations

### Screen 8: Saved Looks
- Grid/list of previously saved outfit combinations
- Filter by occasion or date
- Tap to view full outfit detail
- Delete/unsave option

### Screen 9: Subscription / Upgrade
- Premium tier showcase with elevated, refined design
- Feature comparison (Free vs Premium)
- Stripe-ready upgrade button placeholder
- Not aggressive — feels like an invitation, not a sales pitch

### Screen 10: Settings
- Profile editing
- Body profile updates
- Notification preferences
- Subscription status
- About / Help
- Logout

## 5. Navigation
- **Bottom tab bar** with 4–5 tabs: Home, Wardrobe, Generate, Saved, Profile
- Icons: default #1A2133, active #6E8CA6
- Minimal, refined tab labels

## 6. AI Integration Placeholders
- Outfit generation service with mock responses (realistic outfit combinations)
- Garment classification placeholder (returns mock category/color data on upload)
- Recommendation engine stub that serves curated mock outfits based on occasion
- Structured so real AI can be swapped in later without UI changes

## 7. Premium Gating
- Free tier: up to 20 wardrobe items, 3 outfit generations/day, basic recommendations
- Premium tier: unlimited wardrobe, unlimited generations, detailed style notes, ad-free
- Upgrade prompts placed naturally (not aggressively) when limits are hit

---

## Visual Quality Bar
The final result must feel like a **fashion editorial with embedded intelligence** — not a startup dashboard, not a Pinterest clone, not a shopping app. Calm, structured, premium.

