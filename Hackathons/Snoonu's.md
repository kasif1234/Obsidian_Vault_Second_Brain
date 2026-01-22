Overall Plan:
1. Google Antigravity -> Fast Development 
2. Voice Agents -> Increases chances of winning
3. Excellent Pitch Deck -> Use Faheem's Fanar Pitch Deck and modify, build, renovate it
4. Script -> 
	1. Tell a story
	2. Explain why its a win for Snoonu
	3. 


==IDEA 1==: =============================================================
Here is a hackathon-ready idea that can realistically win because it is (1) high impact for Snoonu, (2) demo-able in 2–3 days, and (3) has clear business KPIs.

### Inputs

1. Craving signature
    
    - food type (shawarma, burger, pizza)
        
    - intensity (light, medium, heavy)
        
    - satisfaction driver (spicy, cheesy, crunchy, etc.)
        
2. Budget guardrail
    
    - max spend now (QAR)
        
    - value mode (cheapest acceptable vs best overall)
        
3. Wearable health signals (daily summaries, not medical)
    
    - sleep duration or quality bucket
        
    - activity level (steps or active minutes)
        
    - recovery proxy (resting HR deviation or “low, ok, high”)
        
4. Mood and energy check-in (30 seconds, optional but powerful)
    
    - current mood (low, ok, good)
        
    - energy level (low, ok, high)
        
    - stress level (low, ok, high)
        
5. Dietary constraints and preferences
    
    - allergies, halal, vegetarian, dislikes
        
    - goal (maintain, fat loss, muscle gain)
        
6. Context signals (Snoonu-native)
    
    - time of day
        
    - recent order history
        
    - delivery distance or ETA tolerance
        

---

### Outputs

1. Ranked “Mood-Smart” fast-food picks (top 3)
    
    - each option is within budget and matches craving
        
    - each option includes a “smart swap bundle” (main + side + drink)
        
2. Mood impact explanation (short labels, not medical claims)
    
    - “sleep low → lighter + higher protein”
        
    - “stress high → avoid sugar spike combo”
        
    - “activity high → add carbs, keep budget”
        
3. One-tap actions
    
    - “Add best bundle to cart”
        
    - “Swap side” or “Swap drink”
        
    - “Cheaper mood-safe option”
        
4. Personal nudges that improve mood without sounding like therapy
    
    - “You will feel better in 30 minutes if you choose this bundle” (worded as a gentle wellness suggestion)
        
    - “Hydration add-on” prompt
        
    - “Smaller portion now, save craving for later” option
        
5. Tracking outputs for your KPIs
    
    - Healthy Order Share flag (healthy-tagged or mood-safe bundle)
        
    - budget adherence (under cap)
        
    - post-order mood check-in (optional 1-tap after eating) to show improvement
        

PRESENTATION ELEMENTS
## Option A: Contrarian, memorable

- **We Don’t Fight Cravings. We Redirect Them.**
    
- **Make Fast Food Behave Like Healthy Food (Without Paying Meal-Prep Prices).**
    
- **Healthy-by-Default, Not Healthy-by-Willpower.**
    

## Option B: KPI-first, judge-friendly

- **Increase Healthy Order Share Without Increasing Spend.**
    
- **Healthy Choices Under Budget: Move Healthy Share From X% to Y%.**
    
- **Same Crave, Better Macro: Healthy Share Up, AOV Stable.**
    

## Option C: “Moment of truth” framing

- **The 30-Second Decision: Budget + Crave + Health.**
    
- **At Checkout, Health Usually Loses. We Change That.**
    
- **Turn “What Should I Eat?” Into One Tap.**
    

## Option D: SuperApp-native framing

- **From Wallet to Wellness: A Snoonu Food Upgrade.**
    
- **A New Daily Habit Loop Inside Snoonu Food.**
    
- **Health Nudges That Convert (Because You Can Order Immediately).**
    

## Option E: Youth and culture-friendly (still professional)

- **Cravings, Solved: Cleaner Picks From Shawarma, Burgers, Pizza.**
    
- **Your Crave, Your Budget, Your Health — One Recommendation.**
    
- **Fast Food, Smarter: The Healthy Swap Engine.**






===========================================================
==IDEA 2==
## Winning idea: Snoonu Flow

### AI dispatch and hotspot planning to cut delivery time and cost

### The problem (what judges care about)

Snoonu loses money and customer trust when:

- Riders are in the wrong places at peak hours
    
- Orders are assigned sub-optimally (too many single trips, late ETAs, missed batching)
    
- ETAs are inconsistent and not “confidence-aware”
    

### The solution

**Snoonu Flow** is an “Ops Co-Pilot” that does two things:

1. **Predicts where demand will be** in the next 15–60 minutes (hotspots by zone).
    
2. **Optimizes rider positioning and order assignment** (batching + routing) to minimize late deliveries and cost.
    

### Core features (MVP scope)

1. **Hotspot Forecast Map**
    

- Input: recent orders (time, zone, vendor type, day of week, weather optional)
    
- Output: heatmap of predicted orders per zone for next time window
    
- Value: stage riders _before_ the rush
    

2. **Smart Dispatch + Batching**
    

- Given incoming orders + available riders, produce assignments:
    
    - batch compatible orders (same direction, time window)
        
    - prioritize SLA (food vs grocery vs pharmacy)
        
    - keep rider workload balanced
        
- Value: fewer late deliveries, fewer empty rider minutes
    

3. **Confidence ETA**
    

- Show ETA as: “23–28 min (high confidence)” instead of one number
    
- Value: fewer cancellations, fewer angry customers
    

### Why it wins

- Directly targets **logistics**, one of their stated tracks
    
- Clear measurable impact (time, cost, SLA, cancel rate)
    
- Demo looks impressive: map + optimizer + real-time simulation
    
- Not “generic AI” — it is operationally grounded
    

---

## What you demo on stage (simple but powerful)

A live dashboard with:

- Doha grid map (zones) with predicted hotspots
    
- A “simulate peak hour” button that generates incoming orders
    
- A dispatch panel showing assignments and routes
    
- Before vs after metrics:
    
    - Average delivery time
        
    - On-time rate
        
    - Rider utilization (active minutes / total minutes)
        

Even with synthetic data, the story is convincing if you show improvement.

---

## Metrics to claim (pick 3 and show them in the demo)

- **On-time rate**: +8% to +15%
    
- **Avg delivery time**: −10% to −20%
    
- **Rider idle time**: −10% to −25%
    
- **Cancel rate (ETA-related)**: −5% to −10%
    

---

## Technical approach (hackathon-feasible)

### Data model (minimal)

- Orders: (pickup_zone, dropoff_zone, created_at, category, prep_time_est)
    
- Riders: (current_zone, status, capacity, shift_end)
    
- Travel time: zone-to-zone matrix (can be approximated)
    

### Algorithms

1. **Hotspot predictor**
    

- Baseline: last-week same hour + moving average
    
- Better: XGBoost/LightGBM regression per zone
    
- Output: predicted order count per zone for next 30 min
    

2. **Dispatch optimizer**
    

- Use **OR-Tools** (Vehicle Routing / assignment) or a greedy heuristic:
    
    - batch by direction similarity + time window
        
    - choose rider that minimizes total lateness + travel time
        
- You do not need perfect routing; you need measurable improvement.
    

3. **ETA confidence**
    

- Train a simple regression for delivery duration
    
- Confidence = quantiles (P50/P90) from residuals by zone/time
    

---

## 2–3 day build plan (team of 4)

- Person 1: Dashboard (React/Next or Streamlit) + map heatmap
    
- Person 2: Hotspot prediction + synthetic data generator
    
- Person 3: Dispatch + batching optimizer (OR-Tools / heuristic)
    
- Person 4: Pitch + metrics + demo script + packaging
    

---

## Pitch in 20 seconds

“Snoonu Flow predicts demand hotspots and optimizes dispatch in real-time. Instead of reacting to orders, Snoonu stages riders early and batches smartly, improving on-time delivery while lowering cost per order. Our demo shows measurable reductions in delivery time and rider idle time using a realistic Doha zone simulation.”
==========================================================
==Pitch Deck Format==
## Pitch structure that tends to win (5 minutes)

1. Problem in one sentence (with KPI)
    
2. Why it matters to Snoonu now (scale, cost, growth)
    
3. Solution (show the demo early)
    
4. How it works (architecture in 20 seconds)
    
5. Results (even if simulated): baseline vs improved
    
6. Rollout plan (2–4 weeks MVP inside Snoonu)
    
7. Risks and mitigations (1 slide)



=====
Lanudary
Prime - fine dining
tamwin - 
electronics
home business
takeway
drive
charity 
my car

====
1. Snoomart
2. Snoosend
3. Scity
4. Laundary
5. Snoonu Market
6. My Car
7. My House
