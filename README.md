# Schlingmann HLF 20 — Beladungstrainer

[Open the trainer](https://evgkar.github.io/fire-truck-3d/)

Interactive reconstruction of the Feuerwehr Liederbach MAN TGM / Schlingmann HLF 20. Four opening cab doors, seven equipment compartments and 44 movable items or transport sets, including 11 cabin items. The single HTML file contains the model, Three.js, Cannon-es, authored textures and lighting environment and works offline.

## Languages

The saved language is restored on load. On a first visit, the browser/system language is used when supported (Deutsch, English or Russian), with Deutsch as the fallback. The loading message is translated before the 3D libraries and model initialize. Language choice is saved locally. Switching language preserves the camera, equipment positions and training score. Interface, item names, descriptions, mass notes, source captions and accessibility labels are translated; original German lettering on the vehicle stays unchanged.

## Interaction

- Use the expand icon beside the language selector for a full-screen scene. The same button or Esc restores the panels without dropping a held item. Browsers without the Fullscreen API expand the scene to fill the page. Camera orientation and training progress are retained.
- Drag empty background to orbit; scroll or pinch to zoom. After "Pick up", dragging anywhere on the scene rotates the camera while the item stays held. A camera gesture never places or drops the item.
- Ctrl + drag pans the view. On a touchscreen, drag with two fingers to pan; changing their distance zooms.
- Click an item for its details. Double-click/double-tap or choose “Pick up” to lift it.
- Point at a storage position to highlight it. Click the item's own position to animate it back into its mount. A wrong mount releases the item and it falls.
- Direct dragging also moves equipment with physics. While carrying, Shift + scroll changes item height, R rotates the item, and Esc releases it. Ordinary scrolling still zooms the camera.
- “Hide cab” removes the cab shell and doors while retaining seats, dashboard, fixed mounts and portable equipment.
- Storage-position buttons provide a keyboard and touch alternative to precise 3D selection.
- “Unload all” and “Load all” handle the complete inventory.

## Training

Items are scattered randomly in front of the truck. Correct placement on the first attempt awards 100 points per item. A wrong mount forfeits that item's points. Dropping onto the ground is not a placement attempt. Loading everything automatically ends the exercise without extra points. The hover highlight never reveals which mount is correct.

## Reconstruction and limits

This is a detailed procedural reconstruction for learning storage positions, not a photographic digital scan or a certified operational simulator. Visible crew-cab equipment and exterior details follow photographs. The exact Liederbach dashboard is not fully documented; its shape follows MAN TGM 13.290 reference vehicles from Dachau (2015) and Günding (2016). Pedals, gauge markings and individual switches remain approximate. Unconfirmed models, masses, dimensions and closed-case contents are identified as such.

The cabin inventory includes two breathing-apparatus sets, a closed red bag, six hand lamps and two handheld radios. Seats, chargers, brackets and wired equipment remain fixed. Closed bags/cases are moved as complete containers without invented contents.

The EISEMANN BSKA 13EV generator is documented at 820 × 440 × 580 mm and 150 kg without its battery. Other masses are estimates. Gravity, inertia, friction and collisions are simulated with simplified rigid-body shapes. Heavy loads use assumed crew assistance; human strength, flexible hoses and operational tool mechanisms are not simulated. Animated docking routes are visual guidance, not collision-planned robotics.

## Sources

- [Feuerwehr Liederbach — HLF 20](https://www.feuerwehr-liederbach.de/hlf-20/): vehicle description and seven original photographs, up to 4592 × 2584.
- [WS Brandschutztechnik — delivery photographs](https://www.ws-brandschutztechnik.de/referenzen/feuerwehrfahrzeuge): eight further images, including crew compartment and pump panel.
- [Kreisbrandinspektion Dachau — Günding 2016](https://www.kbi-dachau.de/florian-guending-401.html): MAN TGM cockpit reference.
- [Kreisbrandinspektion Dachau — Dachau 2015](https://www.kbi-dachau.de/florian-dachau-401-und-402.html): MAN TGM dashboard and seat reference.
- [Original video, 1:34–1:45](https://youtu.be/vlrIXLORpqk?t=94).
- Research details: [equipment catalog](equipment-catalog.json), [cabin equipment](cabin-equipment.json), [reference research](reference-research.json), [cockpit research](cockpit-research.json).

Original reference photographs are not embedded or republished in the game. Sources link to their publishers. Geometry and dashboard textures are authored reconstructions.

## Dependencies

- Three.js r128 — MIT.
- Cannon-es 0.20.0 — MIT.
- [Poly Haven Studio Small 01](https://polyhaven.com/a/studio_small_01), Greg Zaal — CC0, reduced HDR environment.

Library licenses are retained inside the HTML. Validation covers unique storage positions, first-attempt scoring and anti-farming, assisted loading, gravity/contact/collision, release from grip, continuous docking animation, translated inventory and interaction scenarios. Browser checks cover loading, camera views, actual 3D selection, double-click pickup, incorrect placement, language switching and responsive layout.
