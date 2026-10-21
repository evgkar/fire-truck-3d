# Feuerwehr — 3D Beladungstrainer

[Open the trainer](https://evgkar.github.io/fire-truck-3d/)

Interactive reconstructions of two fire engines with four opening cab doors, seven equipment compartments, individually labelled portable equipment and storage training:

- Feuerwehr Liederbach: MAN TGM / Schlingmann HLF 20 — 44 movable items or transport sets, including 11 cabin items.
- Feuerwehr Oberhaching 40/1: Mercedes-Benz Atego 1528 Allrad / Ziegler LF 16/12, 2003 — 80 movable items or transport sets.

Choose a vehicle above the sidebar tabs. The selection is remembered; changing vehicles starts a new exercise. Direct links use `?vehicle=liederbach` or `?vehicle=oberhaching`. The startup camera faces the headlights for all three welcome flashes and then smoothly orbits to the overview. Dragging, zooming or choosing a view cancels the tour immediately; reduced-motion users get a direct transition. The welcome can be skipped or replayed.

## Real 3D assets

The viewer fetches separate GLB geometry and JSON metadata for the selected vehicle. Each standard glTF 2.0 GLB contains PBR material factors, normals, UV coordinates and named groups for the cab shell, doors, shutters and individual tools. Geometry is batched by material within each movable group. Doors retain hinge pivots and equipment retains independent origins. The file can be imported into compatible 3D editors or game engines.

- [Liederbach vehicle GLB](assets/liederbach/scene.glb) · [metadata](assets/liederbach/metadata.json).
- [Oberhaching vehicle GLB](assets/oberhaching/scene.glb) · [metadata](assets/oberhaching/metadata.json).
- Each item's detail card includes a download link to its standalone GLB.

The Oberhaching G6 generator, three foam-agent containers and collecting breeching use embedded PBR colour, normal and metallic/roughness maps. The BSKA 13 labels are UV-authored geometry within the standalone GLB, so these materials and markings travel with the asset. Other equipment retains the browser's procedural surface maps and runtime lettering. Light effects, physics, storage logic and camera movement are implemented by the viewer. To run locally, serve the complete folder over HTTP; opening the HTML directly with `file://` does not permit fetching the asset files.

## Languages

The saved language is restored on load. On a first visit, the browser/system language is used when supported (Deutsch, English or Russian), with Deutsch as the fallback. The loading message is translated before the 3D libraries and model initialize. Language choice is saved locally. Switching language preserves the camera, equipment positions and training score. Interface, item names, descriptions, mass notes, source captions and accessibility labels are translated; original German lettering on the vehicle stays unchanged.

## Interaction

- Use the expand icon beside the language selector for a full-screen scene. The same button or Esc restores the panels without dropping a held item. Browsers without the Fullscreen API expand the scene to fill the page. Camera orientation and training progress are retained.
- Drag empty background to orbit; scroll or pinch to zoom. After "Pick up", dragging anywhere on the scene rotates the camera while the item stays held. A camera gesture never places or drops the item.
- Hold the mouse wheel (middle button) and drag, or use Ctrl + drag, to move the scene forward, backward, left and right along the horizontal plane without changing camera height. On a touchscreen, move two fingers together for the same movement; spreading or pinching them still zooms.
- Click an item for its details. Double-click/double-tap or choose “Pick up” to lift it.
- Point at a storage position to highlight it. Click the item's own position to animate it back into its mount. A wrong mount releases the item and it falls.
- Direct dragging also moves equipment with physics. While carrying, Shift + scroll changes item height, R rotates the item, and Esc releases it. Ordinary scrolling still zooms the camera.
- “Hide cab” removes the cab shell and doors while retaining seats, dashboard, fixed mounts and portable equipment.
- Storage-position buttons provide a keyboard and touch alternative to precise 3D selection.
- “Unload all” and “Load all” handle the complete inventory.
- Successfully docking an individual tool produces one soft green rim glow on its actual shape. The effect fades out, respects reduced-motion preferences and does not trigger on a wrong placement or bulk loading.
- On loading, three synchronized high-beam, hazard and blue-beacon pulses welcome the visitor. Successful individual stowage triggers two short hazard pulses after docking; bulk loading does not trigger a siren or a pulse per item.
- Click a blue beacon or the roof horns to toggle the siren and blue beacons. Click a headlight to toggle steady high beams independently. The Vehicle tab provides the same two controls and can replay the welcome.
- The synthesized two-tone siren plays when audio is permitted, otherwise after the first interaction. The speaker button mutes audio immediately and remembers the preference; light signals remain active. It is not a recording of this particular truck.

## Training

The Training tab provides four guided modes in German, English and Russian:

0. Learn a compartment: face the open compartment, then use the arrows to focus each tool and read its description alongside an original reference photo.
1. Find the compartment: identify a large isolated 3D tool and choose its bay, without a shelf-level answer.
2. Fill a compartment: choose tools from a scrollable visual list and put each into its own mount in the empty compartment.
3. Place one tool: every compartment starts open and empty; place the current tool in its exact mount before receiving the next one.

Each test awards 100 points for a correct first attempt. Incorrect valid answers forfeit only that item's points; closed or nonexistent targets do not consume an attempt. Camera movement remains available while holding equipment. Buttons provide alternatives to precise 3D clicking. Descriptions, source links and location-bearing names are hidden during tests. Three Oberhaching positions that were inferred rather than documented are excluded from tests and marked in learning. Switching to another tab ends the guided exercise and returns to free exploration.

The dated [evidence catalog](training-mode-research.json) covers all 124 items, with source-qualified DE/EN/RU descriptions, 54 photographic crops and full-frame compartment photos where no individual view is available. Crops are display windows into real photographs, never generated tool images. The 3D previews are explicitly labelled reconstructions. Learning cards link the original sources.

The retained free loading game is available below the guided mode selector:

Items are scattered randomly in front of the truck. Correct placement on the first attempt awards 100 points per item. A wrong mount forfeits that item's points. Dropping onto the ground is not a placement attempt. Loading everything automatically ends the exercise without extra points. The hover highlight never reveals which mount is correct.

## Reconstruction and limits

The Liederbach exterior pass refines separate optical chambers, reflector surfaces, indicator lenses, rear light clusters, passenger-side observation mirrors, cab handles, shutter bars and towing hardware. The four chrome roof fittings are hollow horn bells, following the photographs. Paint, glass, rubber, fabric and brushed metal have separate surface responses. The visible shapes follow the vehicle photographs; the exact electrical assignment of unlit headlight/rear-light sections remains a reconstruction.

This is a detailed procedural reconstruction for learning storage positions, not a photographic digital scan or a certified operational simulator. Visible crew-cab equipment and exterior details follow photographs. The exact Liederbach dashboard is not fully documented; its shape follows MAN TGM 13.290 reference vehicles from Dachau (2015) and Günding (2016). Pedals, gauge markings and individual switches remain approximate. Unconfirmed models, masses, dimensions and closed-case contents are identified as such.

The Liederbach cabin inventory includes two breathing-apparatus sets, a closed red bag, six hand lamps and two handheld radios. The Oberhaching cabin adds two removable warning triangles, two rope bags, two handheld radios and a lamp; the door-mounted items follow their door hinges. Seats, chargers, brackets and wired equipment remain fixed. Closed bags/cases are moved as complete containers without invented contents.

The Liederbach EISEMANN BSKA 13EV generator is documented at 820 x 440 x 580 mm and 150 kg without its battery. The Oberhaching generator is marked BSKA 13 in the supplied photograph; its model dimensions and mass are estimates. Other masses are estimates. Gravity, inertia, friction and collisions are simulated with simplified rigid-body shapes; each vehicle uses its own body and wheel collision profile. Heavy loads use assumed crew assistance; human strength, flexible hoses and operational tool mechanisms are not simulated. Animated docking routes are visual guidance, not collision-planned robotics.

## Sources

- [Feuerwehr Liederbach — HLF 20](https://www.feuerwehr-liederbach.de/hlf-20/): vehicle description and seven original photographs, up to 4592 × 2584.
- [WS Brandschutztechnik — delivery photographs](https://www.ws-brandschutztechnik.de/referenzen/feuerwehrfahrzeuge): eight further images, including crew compartment and pump panel.
- [Gemeinde Liederbach — Amtsblatt, 26 November 2016](https://www.liederbach.eu/datei/de/gemeinde/-/2599/extLink): official handover and commissioning history.
- [Additional detail research](detail-research-v5.json): checked sources, visual observations, uncertain identifications and excluded vehicles.
- [Kreisbrandinspektion Dachau — Günding 2016](https://www.kbi-dachau.de/florian-guending-401.html): MAN TGM cockpit reference.
- [Kreisbrandinspektion Dachau — Dachau 2015](https://www.kbi-dachau.de/florian-dachau-401-und-402.html): MAN TGM dashboard and seat reference.
- [Original video, 1:34–1:45](https://youtu.be/vlrIXLORpqk?t=94).
- Research details: [equipment catalog](equipment-catalog.json), [cabin equipment](cabin-equipment.json), [reference research](reference-research.json), [cockpit research](cockpit-research.json).
- [Feuerwehr Oberhaching — LF 16/12 40/1](https://www.feuerwehr-oberhaching.de/fahrzeuge/lf-1612-401/): official specifications and ten exterior photographs up to 1920 x 1280.
- [User-provided Miro inventory](https://miro.com/app/board/uXjVKwGF5Ug=/) and fifteen supplied compartment/interior photographs: Oberhaching storage layout and identification.
- [Oberhaching equipment catalog](oberhaching-catalog.json) and [research](oberhaching-research.json): confirmed names, container contents, uncertain identifications and model limits. Contents hidden inside closed containers are described without inventing their appearance.

Eight original photographs supplied by the project owner are included for Oberhaching reference cards. Other photographs are displayed from the original publisher with attribution and a link; the site handles unavailable external images explicitly. No third-party photo redistribution license is assumed. The reference catalog also links newly located Oberhaching originals at approximately 7.5–9K resolution; those large files are not loaded automatically. Geometry and dashboard textures are authored reconstructions.

The October 2026 geometry pass replaces the incorrect open-frame MAN generator with the photographed enclosed EISEMANN BSKA 13EV cabinet, and separately corrects the Mercedes BSKA 13 controls. Storz fittings have actual hollow bores, seals and opposing claws; hydraulic connectors have their own construction. The WEBER reel has real flange perforations and the photographed yellow/red cheeks. Breathing-apparatus harnesses use flat straps and buckles. Confirmed maker lettering follows the moving item. These refinements do not turn the reconstruction into a photogrammetric scan: unseen surfaces, unmeasured proportions and unconfirmed product variants remain uncertain.

## Dependencies

- Three.js r128 — MIT.
- Cannon-es 0.20.0 — MIT.
- [Poly Haven Studio Small 01](https://polyhaven.com/a/studio_small_01), Greg Zaal — CC0, reduced HDR environment.

Library licenses are retained inside the HTML. Validation covers unique storage positions, first-attempt scoring and anti-farming, assisted loading, gravity/contact/collision, release from grip, continuous docking animation, translated inventory and interaction scenarios. Browser checks cover loading, camera views, actual 3D selection, double-click pickup, incorrect placement, language switching and responsive layout.
