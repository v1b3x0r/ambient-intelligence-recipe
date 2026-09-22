# Ambient Intelligence Recipe (Not a Product.)

A quick note before you start: this repository is not a complete system or a piece of software that you can simply run and use.

It is a recipe.

I'm putting together the ingredients, ideas, and ways of connecting different systems that can be used to build what we call Ambient Intelligence (AmI).

The current version of this document does not describe the complete system I have in mind. It is based on a prototype that I assembled and have been running in my own home for roughly six months.

Why build something like this in the first place?

I live alone, and taking care of multiple rooms means constantly turning lights and appliances on and off. Existing smart-home systems can help, but interacting with them often still means taking out a phone, opening an app, finding the right device, and pressing a button. More importantly, you still can't really talk directly to the place around you.

There are also much simpler everyday problems.

Sometimes I come home around 10 or 11 PM with the back of the car full of things. I may have forgotten the remote inside the house, and sometimes I don't even have a free hand to turn on the lights. I have to walk around turning things on, unload everything, and then walk back around turning them off again.

It's a small waste of effort at home.

But when the same idea is applied to a hotel or a much larger place, the nature of the problem changes. The basic topology can still be understood in a similar way, but as the scale and risk increase, so does the engineering complexity.

This document will stay within the scope of a home-scale prototype.

Managing hundreds or thousands of lights and fans is obviously different from managing one light and one fan in a room. But at home, something like a sprinkler system can be simple enough to experiment with: when the right context is present, the house can decide to activate a water pump.

The same basic ideas can extend to larger environments, but larger systems require significantly more engineering, infrastructure, safety considerations, and operational work.

This is not a formal academic paper.

Think of it more like notes from a nerd who tried assembling a bunch of technologies at home, found that they actually worked together, and decided to share the recipe.

---

<img width="1536" height="1024" alt="Ambient Intelligence prototype" src="https://github.com/user-attachments/assets/22656e00-6346-41bf-bc59-5ae3b3d071d4" />

---

## What is Ambient Intelligence made of? (The basics)

Most of these components are fairly accessible and can be found in many countries.

For my prototype, I mainly use Shelly devices for sensors and actuators. Presence can come from the iOS or Android ecosystem, or from entirely different sources.

- **Sensor:** An important component for bringing context from the physical world into its digital representation. Sensor observations enter through the ingest layer and can later contribute to state, interpretation, and decisions.

- **Actuator:** Think of an actuator as an organ that allows a place to act on the physical world. The place might be a room, a house, or something much larger. The basic primitive may be as simple as on/off, or any other state the device is capable of controlling.

- **Time (as context):** What time is it? What day is it? When are sunrise and sunset? How long has today's sunlight lasted?

- **Time (as history):** Historical observations and events that can be used to establish baselines and eventually learn the behavior of individual devices or entities.

- **Presence:** Possibly one of the most important pieces. Without presence, it becomes much harder for the system to understand who enters or leaves a place, where they are, and when it happened.

- **Rules:** Used when a person wants to express an action as a condition. For example:  
  *"Water the garden every day, except when it's raining or when the soil is already too wet."*

## Topology

```plaintext
People + Environment
        ↓
Presence + Sensors + External Context
        ↓
      Ingest
        ↓
 State / History
        ↓
 Rules / Interpretation
        ↓
 Decision + Authority
        ↓
      Actions
        ↓
Lights / Fans / TV / Pumps / Sprinklers
```

* I can't say how often I'll update, but more soon.
