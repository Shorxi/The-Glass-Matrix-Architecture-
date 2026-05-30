# Carrier-to-Board Interconnect Specification

## 1. Universal Carrier Concept

The MVC carrier is a **passive, socket-agnostic interposer**. It does not define:
- Silicon logic,
- Mainboard form factor,
- Proprietary socket geometry.

It standardizes:
- Die-to-carrier interface,
- Carrier-to-board metallization,
- Fluidic inlet/outlet ports,
- Optional inductive control bus.

## 2. Top-Level: Die-to-Carrier

- Connection: Anisotropic Conductive Film (ACF).
- Contact pads: AJP silver nano-pads.
- Target contact resistance: R_c < 10 mΩ per Z-axis contact.
- Thermal coupling: direct contact to internal cooling channels (liquid metal TIM or
  direct dielectric fluid contact at Thermal Exclusion Zones).

## 3. Bottom-Level: Carrier-to-Board

### 3.1. Universal UBM Stack

Bottom TGVs terminate in a Ti/Cu/Ni/Au stack:

- Ti: 50 nm (adhesion to glass).
- Cu: 500 nm (current conduction).
- Ni: 3 µm (diffusion barrier).
- Au: 50 nm (oxidation shield, solder wetting).

Compatible with:
- SAC305 lead-free solder,
- Bismuth-based alloys,
- LGA gold pads.

### 3.2. Universal Micro-Fluidic Manifold (UFM)

- Circular inlet/outlet ports aligned with internal channels.
- Sealing: aerospace-grade Viton micro O-rings.
- Pressure regime: up to 6 bar system pressure.
- Pressure drop across transition:  
  ΔP_transition = ζ · ρ · v² / 2, with ζ ~ 0.5 for abrupt contraction/expansion.

Any vendor may attach their own external pump and loop hardware.

### 3.3. High-Frequency & Inductive Interfaces

- Sub‑THz data: Z_0 ~ 50 Ω, L_via ~ 0.1 nH, board C_pad tuned by the PCB vendor.
- Target return loss: S11 < −20 dB.
- Co2Z hexaferrite inserts: planar inductive control bus, k > 0.9 across up to 2 mm gap.

This interface spec is intentionally **form-factor agnostic**. Vendors map their own BGA/LGA
footprints onto the provided UBM and fluidic hardpoints.
