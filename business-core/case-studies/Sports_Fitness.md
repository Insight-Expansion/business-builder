---
**Document:** Sports_Fitness.md
**Version:** 1.1
**Last Updated:** 2026-02-18
**Owner:** Business Development
**Update Frequency:** Monthly
**Parent:** Case_Studies_Library.md

**Synthesized From:**
- `Founder_Track_Record.md` v1.0 (coverage: ~100% for sports/fitness projects)

**What Changed:**
- v1.0 (2026-02-10): Initial creation — 2 Nexrizen case studies
- v1.1 (2026-02-18): Added 1 founder track record project (F20: CITYROW/WaterRower)

**Downstream Dependencies:**
- README.md - Index file references this
- Case_Studies_Library.md - Master index references this
- Sales playbooks and proposals may reference specific cases
- Sports tech vertical marketing materials
---

# Sports & Fitness Case Studies

**Total Cases:** 3 (2 Nexrizen + 1 Founder Track Record)
**Status Mix:** 1 phase 1 complete (phase 2 pending) / 1 discovery/solution architecture + 1 completed (pre-Nexrizen)

Sports technology represents a specialized vertical where Nexrizen's computer vision and real-time video analysis capabilities shine. These case studies demonstrate expertise in biomechanics, frame-precise temporal detection, and mobile edge computing—all critical for performance analysis applications.

---

## Quick Reference

| Case Study | Client | Status | Budget | Key Metric |
|------------|--------|--------|--------|------------|
| Baseball Phase Detection | SportsFX | 🚧 Phase 1 Complete | Premium | ~70% → improved accuracy |
| Live Real-Time Mobile Metrics | SportsFX | 📝 Solution Architecture | TBD | 4-second latency target |
| **Founder Track Record** | **Pre-Nexrizen** | | | |
| F20: CITYROW → WaterRower Acquisition | Gabe (Fractional CTO) | ✅ Completed | — | Led tech through acquisition |

---

## Case Study 8: SportsFX Baseball Phase Detection

**Client Type:** Sports Technology / Baseball Analytics
**Project:** AI-powered baseball pitching phase detection from video
**Status:** 🚧 Phase 1 Complete, Phase 2 Pending

### Problem
- Current Gemini-based system achieves only ~70% accuracy in phase detection
- Stochastic model output (different results each run even with temperature=0)
- Need frame-level precision for biomechanical analysis
- 200+ video dataset requires consistent annotation

### Solution
Deep learning approach using TCN/transformer models for temporal segmentation with frame-level prediction (not timestamp-based) for multi-framerate support. Key event detection: arm cocking, stride, acceleration, ball release. Integrates 3D mesh data (SMPL body model) for occluded views and multi-view consistency.

### Technologies
- Python
- PyTorch
- Temporal Convolutional Networks (TCN)
- SMPL 3D body models
- Computer Vision
- Sports biomechanics analysis

### Timeline
Phase 1 delivered (discovery & research), Phase 2 pending (data collection)

### Team
Wei + CV specialists

### Sales Usage
Reference for sports tech clients needing video AI, biomechanics analysis, or frame-precise temporal detection. Perfect for performance analysis, coaching tools, or any domain requiring precise event detection in video (medical procedures, manufacturing quality control, etc.).

---

## Case Study 9: SportsFX Live Real-Time Mobile Metrics

**Client Type:** Sports Technology / Mobile App
**Project:** Real-time baseball metrics from live mobile video (B4 app competitor)
**Status:** 📝 Discovery / Solution Architecture

### Problem
- Current app requires post-processing (not real-time)
- Competitors (B4 app) provide instant metrics on-device
- Need to run on iPhone (Flutter app complicates Apple ML integration)
- 4-second latency requirement

### Solution
On-device ML inference using Core ML / Apple Vision Framework with real-time pose estimation optimized for edge devices.

**Metrics - Hitting:**
- Exit velocity
- Bat speed
- Launch angle
- Projected distance

**Metrics - Pitching:**
- Velocity
- Spin rate
- Horizontal/vertical break

Ball and bat tracking in real-time with ground plane detection for 3D reconstruction.

### Technologies
- Flutter
- Core ML
- Apple Vision Framework
- On-device ML
- Computer Vision
- Real-time video processing

### Timeline
Target launch before June 2026

### Team
Wei + mobile ML specialists

### Sales Usage
Showcase for mobile AI, edge computing, real-time video analysis. Perfect for sports tech startups seeking investor-ready features, fitness apps, or any application requiring immediate feedback from video without cloud dependency (security, latency, offline capability).

---

## Founder Track Record (Pre-Nexrizen)

> **Important:** These are NOT Nexrizen client projects. Frame them as "our founders' track record" or "what our team has built before," not as Nexrizen deliverables.

---

### F20: CITYROW → WaterRower Acquisition

**Client Type:** Fitness Tech / Connected Fitness
**Role:** Senior Software Engineer (Sep 2021 – Jul 2022) → Fractional CTO (Mar 2023 – Mar 2024)
**Status:** ✅ Completed (client acquired January 2024)

#### Problem
CITYROW, a connected fitness company, needed technical leadership to optimize their digital platform and position the company for strategic outcomes (acquisition).

#### Solution
- Initially joined as Senior Software Engineer, elevated to Fractional CTO
- Spearheaded tech strategy aligned with business goals
- Optimized digital fitness platform performance
- Drove product innovation that made the company attractive for acquisition

#### Results
- **CITYROW acquired by WaterRower** (January 2024)
- Technology strategy was a key factor enabling the acquisition
- 2.5 years total engagement (engineer → CTO → acquisition)

#### Technologies
Full-stack web development, digital fitness platform, product strategy

#### Team
Gabe (Fractional CTO) + engineering team

#### Client Testimonial
> "An incredible asset... absolute game changer for us." — Helaine Knapp, Founder & CEO, CITYROW

#### Sales Usage
**Use when:**
- Selling Fractional CTO services (this is the gold-standard example)
- Demonstrating ability to drive acquisition outcomes
- Proving business impact beyond code (strategy → exit)
- **Verticals:** Fitness tech, consumer apps, companies positioning for acquisition

**Key proof point:** This is the primary exit story for Gabe — proves he can lead tech strategy that creates company-level outcomes.

---

## Sports & Fitness Portfolio Summary

### Technical Capabilities Demonstrated

**Computer Vision:**
- Temporal segmentation (phase detection)
- 3D body mesh reconstruction (SMPL models)
- Ball/bat tracking
- Ground plane detection

**Real-Time Processing:**
- On-device inference (Core ML)
- 4-second latency targets
- Multi-view consistency
- Edge computing optimization

**Biomechanics:**
- Pitching phase analysis (arm cocking, stride, acceleration, release)
- Hitting metrics (exit velocity, bat speed, launch angle)
- Spin rate calculation
- Break analysis (horizontal/vertical)

### Sales Strategy

**Position Nexrizen as specialists in:**
1. **Frame-precise video analysis** (not just general CV)
2. **Real-time mobile ML** (on-device, not cloud-dependent)
3. **Sports biomechanics** (not just generic tracking)
4. **Competitive differentiation** (helping startups beat incumbents like B4 app)

**Target Customers:**
- Sports tech startups (baseball, softball, golf, tennis)
- Fitness apps (form analysis, rep counting)
- Coaching platforms (video analysis tools)
- Performance analysis tools (biomechanics, injury prevention)
- Youth sports platforms (parent/coach tools)

### Expansion Opportunities

**Sports Verticals:**
- **Golf:** Swing analysis, club tracking, ball flight
- **Tennis:** Serve analysis, ball tracking, court position
- **Soccer:** Player tracking, passing analysis, formation detection
- **Basketball:** Shot form, release angle, arc analysis
- **Swimming:** Stroke analysis, turn efficiency
- **Running:** Gait analysis, stride length, cadence

**Adjacent Markets:**
- **Physical Therapy:** Movement analysis, form correction
- **Fitness Coaching:** Exercise form, rep counting
- **Dance/Gymnastics:** Choreography analysis, skill progression
- **Martial Arts:** Technique analysis, sparring analysis

### Competitive Advantages

1. **Frame-level precision** - Not timestamp-based (supports any framerate)
2. **3D mesh integration** - Handles occluded views better than 2D-only
3. **On-device processing** - Privacy, latency, offline capability
4. **Biomechanics expertise** - Not just tracking, but understanding sports science
5. **Production-ready** - Not research projects, but investor-ready products

### Key Differentiators

**vs Traditional Motion Capture:**
- No markers/sensors required
- Works with standard phone cameras
- Accessible price point

**vs Cloud-Based Solutions:**
- Real-time feedback (no upload wait)
- Works offline
- Privacy (video stays on device)

**vs Generic CV Platforms:**
- Sports-specific training data
- Biomechanics-informed models
- Coaching-relevant metrics

---

**Last Updated:** 2026-02-10
