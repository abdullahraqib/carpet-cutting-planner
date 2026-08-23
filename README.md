# Carpet Cutting Planner

Browser-based carpet cutting planning tool for orthogonal (90-degree corner) rooms.

## Current test build

The application is intentionally deployable as a static Vercel site. The main application is in `index.html` so there is no build step or dependency installation required.

### Included

- Draw rooms corner-by-corner.
- Horizontal/vertical wall constraint.
- 90-degree room geometry.
- Enter actual wall dimensions in millimetres.
- Reconstruct and scale room geometry from the entered dimensions.
- Save multiple rooms in a room library using browser local storage.
- Edit room names and dimensions.
- Default 4000 mm carpet roll width, with adjustable roll width.
- Drag room shapes onto the roll.
- Duplicate room instances by dragging the same room again.
- Move pieces with pointer drag.
- Optional grid snapping.
- 90-degree rotation.
- Collision detection between room polygons.
- Prevent pieces from extending beyond the roll width.
- Required carpet length calculation.
- Approximate material/waste calculation.
- Basic automatic stacking arrangement.
- Zoom controls.
- Project name and browser persistence.

## Important limitation

The automatic arrangement is deliberately a basic first-pass arrangement. It is **not yet a production-grade nesting optimiser**. The next development stage should implement a proper orthogonal polygon nesting algorithm that tests rotations and candidate positions and minimises the required roll length while respecting the 4000 mm roll width.

## Testing checklist

1. Add a simple rectangle such as 4000 x 3000 mm.
2. Add an L-shaped room, e.g. walls 4000, 2000, 1500, 1000, 2500, 3000 mm, ensuring the dimensions close.
3. Drag both rooms onto the roll.
4. Move them until they touch without overlapping.
5. Rotate a room and verify the 4000 mm boundary.
6. Change roll width and verify the boundary updates.
7. Refresh the browser and verify rooms/layout remain stored.
8. Test invalid dimensions and overlapping pieces.

## Deployment

The repository can be imported directly into Vercel as a static site. No environment variables are required for the current version.
