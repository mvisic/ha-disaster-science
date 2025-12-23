# Architecture

## Purpose

The `ha-disaster-science` integration provides **proximity-based hazard awareness** in Home Assistant using Disaster Science APIs.

Rather than exposing raw, state-wide datasets, the integration focuses on **events relevant to the user’s home or defined locations**, enabling targeted alerts and automations while minimising alert fatigue.

The integration is designed to be:
- Home Assistant–native
- Low-noise and high-signal
- Flexible enough to support multiple hazard types over time

---

## Design Principles

### 1. Home Assistant–first
- Follows Home Assistant integration best practices
- Uses Home Assistant’s built-in location model (`zone.home`)
- Exposes entities designed for automations, not dashboards alone

### 2. Proximity over volume
- Hazards are filtered based on distance from the home location
- Users define a radius of interest
- Only hazards within this radius influence entity state

### 3. Separation of concerns
- Disaster Science APIs provide authoritative data and geospatial intelligence
- Home Assistant handles:
  - Automations
  - Notifications
  - Dashboards
  - Audio and visual alerts

### 4. Minimal entities, rich attributes
- Avoids entity sprawl
- Exposes a small number of summary entities
- Provides detailed context via attributes

---

## High-Level Data Flow

