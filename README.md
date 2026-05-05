# tec-works/assests — Urban Crime Empire asset library

200 categorized GLB assets generated for the **Urban Crime Empire** project.

## Folder layout

```
assets/
  avatars/        # 100 humanoid GLBs, organized by role
    bosses/       (10)
    civilians/    (20)
    cops/         (10)
    gang_blue/    (10)
    gang_green/   (10)
    gang_red/     (10)
    players/      (20)
    swat/         (10)
  vehicles/       # 100 vehicle GLBs, organized by category
    boats_aircraft/   (10)
    motorcycle/       (10)
    muscle_classic/   (10)
    offroad_military/ (10)
    police/           (10)
    sedan/            (10)
    sports/           (10)
    suv_pickup/       (10)
    truck_heavy/      (10)
    van_commercial/   (10)
  fonts/, images/, props/, weapons/    # supporting 2D/3D assets

vehicles/meshes/    # legacy 11-vehicle generic set (deprecated, kept for compat)
```

## Naming convention

Every avatar and vehicle GLB is prefixed with a 3-digit ID (`001_*.glb` …
`100_*.glb`) that matches the `id` field in the manifests. The prefix is
canonical and never changes — code can reference assets either by filesystem
glob *or* by ID via the in-game `AvatarRegistry` / `VehicleRegistry` autoloads.

## Manifests

- `avatar_meshes.json` — 100 entries with `id`, `role`, `type`
  (`third_person` / `friendly` / `enemy`), and the original generation URL.
- `vehicle_meshes.json` — 100 entries with `id`, `category`, `name`,
  `bbox` (Vector3 in meters for chassis collider sizing), and the source URL.

## Usage in Godot

The `.import` sidecars are committed alongside every GLB so this folder is
drop-in usable in any Godot 4.6 project — copy the `assets/` tree into your
project root and the editor will resolve UIDs on first import.

## Source

Generated alongside the **Urban Crime Empire** project (a Vice City–style 3D
sandbox built on the Moonlake Godot template). The game wires this asset
library through the `AvatarRegistry` / `VehicleRegistry` autoloads — see the
project's `AGENTS.md` for integration details.
