# Atman App - Requirements Specification Document

## 1. Project Overview

### 1.1 Project Name
Atman - Personalized Lifestyle & Health Intelligence App

### 1.2 Vision Statement
To create an AI-powered ecosystem that democratizes product knowledge. Atman aims to become the "Wikipedia of Indian Consumer Products"—built by the community, verified by AI, and personalized for every unique biological profile.

### 1.3 Mission Statement
Enable informed health decisions for Indian consumers through instant ingredient transparency and intelligent, automated stock management.

### 1.4 Target Audience
- **Primary**: Health-conscious individuals (18-45) with specific skin/health goals
- **Secondary**: Users with severe allergies or dietary restrictions
- **Tertiary**: Tech-savvy homemakers seeking inventory organization

## 2. Scope Definition

### 2.0 Hackathon MVP Scope (What We Are Building Now)
To demonstrate technical feasibility within the hackathon timeframe, we are focusing on a specific "Golden Flow":

- **Single User Profile**: Lactose Intolerant + Gym Goal context
- **Single Product Category**: Protein Supplements & Skincare
- **Core Feature Loop**: Scan → Textract OCR → Bedrock Analysis → Safety Verdict (Yes/No) → Suggest 1 Alternative
- **Note**: Inventory tracking and Affiliate linking are architectural stubs for this version

### 2.1 Core Features (Full Product Vision)

#### 2.1.1 Intelligent Scanning System (Barcode First)
- **FR-001**: Users scan product barcodes using the device camera for instant identification
- **FR-002**: Product Not Found Workflow: If a barcode is not in the database, the system triggers "Full Product Scan Mode"
- **FR-003**: In Full Scan Mode, users capture images of the product's front and ingredient label
- **FR-004**: System uses OCR to extract text only during Full Scan Mode to create a new product entry
- **FR-005**: System retrieves ingredient data and health scores instantly for recognized barcodes

#### 2.1.2 Multi-Modal Input Support (The "Anywhere" Scanner)
- **FR-005a**: Share Intent Support: Users can share product links directly from e-commerce apps (Amazon, Blinkit, Zepto) to Atman for instant analysis without scanning
- **FR-005b**: Screenshot Analysis: Users can upload screenshots of products from social media (Instagram/YouTube) for identification via AI Vision

#### 2.1.3 User Profile & Health DNA
- **FR-006**: Users create a "Health DNA" profile (Allergies, Skin Type, Dietary Goals)
- **FR-007**: System allows specific exclusion filters (e.g., "No Parabens," "Vegan Only")
- **FR-008**: System maintains a digital "pantry" of currently owned products
- **FR-009**: Users can manually override current stock levels in case of exceptions

#### 2.1.4 Compatibility & Safety Engine (Two-Layer Shield)
- **FR-010**: Layer 1 (Universal Blacklist): System automatically flags products containing globally banned or toxic substances (e.g., Mercury, Steroids) regardless of user profile
- **FR-011**: Layer 2 (Personal Filter): System cross-references ingredients with the user's Health DNA for individual compatibility
- **FR-012**: System assigns a Compatibility Score (0-100) for every scanned product
- **FR-013**: System translates complex chemical names into plain English (e.g., "Tocopherol" → "Vitamin E")

#### 2.1.5 Community Product Database & Integrity
- **FR-015**: A centralized database of Indian products (FMCG, Skincare, Pharma)
- **FR-016**: Crowdsourcing: Users earn points/karma for adding new products via "Full Product Scan"
- **FR-017**: AI Verification: An automated verification layer checks user-submitted ingredient data against known chemical dictionaries before publishing

### 2.2 Advanced Intelligence (Phase 2 Roadmap)

#### 2.2.1 Consumption Prediction (The "Never Run Out" Engine)
- **FR-018**: Smart Onboarding: Upon scanning a product, the system prompts the user to log the "Open Date" with a single tap
- **FR-019**: Algorithmic Calculation: System automatically calculates the "Projected Empty Date" using the formula: (Product Volume / Avg Daily Category Usage)
- **FR-020**: Smart Defaults: System provides AI-generated usage estimates (e.g., "Standard usage for 200ml Shampoo = 45 days")
- **FR-021**: Adaptive Learning: System learns from user behavior to refine future predictions
- **FR-022**: Smart Reminders: Push notification sent 3-7 days before the projected empty date

#### 2.2.2 Smart Buying (Affiliate Model)
- **FR-023**: System displays current prices for the scanned product across major retailers (Amazon, Flipkart, Blinkit)
- **FR-024**: "Buy Now" buttons redirect users to external retailer apps (Affiliate Links)
- **FR-025**: System tracks price history to alert users of "Lowest Price" moments

#### 2.2.3 Personalized Recommendations
- **FR-026**: If a scanned product has a low safety score, the system suggests 3 "Cleaner" alternatives
- **FR-027**: Recommendations are ranked by Compatibility Score and Price

## 3. Non-Functional Requirements

### 3.1 Performance & Reliability
- **NFR-001**: Barcode lookup response time < 1 second
- **NFR-002**: "Full Product Scan" (OCR + Analysis) processing time < 8 seconds
- **NFR-003**: App functional on low-bandwidth (4G/3G) networks
- **NFR-004**: Offline Mode: Cache recently scanned products for viewing without internet

### 3.2 Security & Privacy
- **NFR-005**: Health data (allergies/conditions) must be encrypted at rest and in transit
- **NFR-006**: Anonymized data used for ML training (no PII attached to consumption patterns)
- **NFR-007**: Compliance with India's DPDP (Digital Personal Data Protection) Act

### 3.3 Usability
- **NFR-008**: "One-Thumb" interface design for quick scanning while shopping
- **NFR-009**: Color-blind friendly alerts (using icons + colors, not just colors)
- **NFR-010**: Support for Hindi and English interface

## 4. Technical Requirements (Architecture)

### 4.1 Frontend
- **TR-001**: React Native (iOS/Android) for the mobile client
- **TR-002**: Vision Camera library for high-speed barcode detection
- **TR-002a**: Intent Filter Configuration to handle shared text/URLs from external apps

### 4.2 Backend & Data
- **TR-003**: AWS Lambda for serverless business logic
- **TR-004**: DynamoDB for high-speed product/user lookups
- **TR-005**: OpenSearch for fuzzy matching product names from shared URLs

### 4.3 AI & ML Services
- **TR-006**: Amazon Textract for Ingredient Label OCR (Full Scan Mode)
- **TR-007**: Amazon Bedrock (Claude/Titan) for interpreting ingredient safety
- **TR-008**: Amazon Forecast for predicting stock depletion dates (Roadmap)

## 5. Business Requirements (Revenue Model)
- **BR-001**: Affiliate Revenue (Commissions from Amazon/Flipkart links when users purchase via "Buy Now")
- **BR-002**: Promoted Products (Brands pay to be suggested as 'Clean Alternatives' in recommendation slots, marked as "Sponsored")
- **BR-003**: Data Insights (B2B): Aggregated consumption data sold to brands to improve inventory planning

## 6. Risk Assessment

### 6.1 Critical Risks
- **Risk-01**: AI Hallucination: The AI might misidentify a safe ingredient as harmful
  - **Mitigation**: Implement a "Confidence Score" threshold. If confidence is low, flag for human review. Display "Not Medical Advice" disclaimers
- **Risk-02**: Missing Barcode Data: Indian local brands often lack centralized barcode data
  - **Mitigation**: Gamify the "Full Product Scan" to encourage users to build the database for us
- **Risk-03**: Dynamic Ingredient Lists: Brands change formulas without changing barcodes
  - **Mitigation**: Prompt users to "Re-scan Label" every 6 months to verify ingredients

## 7. Success Criteria

### 7.1 MVP Success
- **SC-001**: Scan-to-Result time is under 3 seconds for known products
- **SC-002**: Database grows to 1,000 verified products within the first month
- **SC-003**: 90% accuracy in "Full Product Scan" text extraction via Textract

## 8. Strategic Value (The "Why We Win" Factors)

### 8.1 Marketplace Hygiene
- **SV-001**: Return Rate Reduction: By validating biological compatibility before purchase, Atman prevents "Trial & Error" buying, significantly reducing expensive reverse logistics for platforms like Amazon/Nykaa
- **SV-002**: Brand Reputation Defense: Filters out the "wrong" customers (e.g., Oily Skin users buying Dry Skin cream) to prevent unfair 1-star reviews based on incompatibility rather than product quality

### 8.2 The "Neutral Guardian" Advantage
- **SV-003**: Unlike Blinkit/Zepto which are incentivized to sell, Atman is incentivized to protect, creating high user trust as an unbiased third-party intelligence layer