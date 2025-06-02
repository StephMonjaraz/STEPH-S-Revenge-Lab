# 🛠️ KiCad Design Workflow: Schematic ↔ PCB

This guide explains the complete workflow in **KiCad**, placing the **Schematic Editor** and **PCB Editor** side by side — as if you're reading a double-page layout. Use it as a reference during the full design process.

| 📘 **Schematic Editor** | 🧩 **PCB Editor** |
|------------------------|------------------|
| 🔧 The schematic is a **symbolic representation** of your circuit. It shows all components (via symbols) and their logical connections. <br><br>It's created first and defines the logic of your design. | 🔧 The PCB is the **physical realization** of your schematic. It places the **footprints** of components and routes copper tracks between them. |
| 🧰 The Schematic Editor is a **separate window** in KiCad where components are placed and connected. It follows an **integrated workflow** with the PCB. Changes sync both ways. | 🧰 The PCB Editor is another dedicated window. It reads the schematic’s connectivity and helps lay out components on a real board while enforcing rules and manufacturability. |
| 🚀 **Start here**: <br>1. Create a new project<br>2. Open Schematic Editor<br>3. Configure the symbol libraries if prompted | 🚀 **Then open**: <br>1. PCB Editor via Project Manager<br>2. It auto-loads the `.kicad_pcb` file<br>3. Go to `File → Board Setup…` to define layers, rules, and net classes |
| 🧭 Navigation:<br>- Pan: middle/right mouse<br>- Zoom: scroll wheel / `F1`, `F2`<br>- Toolbars (left = view, right = tools)<br>- Hotkeys: `'A'` to add, `'W'` to wire, `'L'` to label | 🧭 Navigation:<br>- Same pan/zoom as schematic<br>- Left toolbar: display settings<br>- Right toolbar: routing tools<br>- Appearance Panel: change active layer, color, visibility<br>- Selection Filter: manage object types |
| 🧩 Add symbols via `'A'`<br>- Search in libraries<br>- Use filter box<br>- Choose from 'Device' for basics | 📐 After importing from schematic (`F8`):<br>- Draw board outline in `Edge.Cuts` layer<br>- Use rectangle, arc, line, bezier tools<br>- Make sure the outline is a **closed, clean shape** |
| ✏️ Select and move:<br>- Click, Shift+click<br>- `'M'` to move, `'G'` to drag<br>- `'R'` to rotate, `'Del'` to delete | 📌 Place and orient footprints:<br>- `'M'` to move, `'R'` to rotate, `'F'` to flip side (mirrored)<br>- Follow mechanical & electrical layout constraints<br>- Use ratsnest for placement guidance |
| 🔌 Wiring:<br>- Use `'W'` to draw wires<br>- Click pin-to-pin or hover-start<br>- Power: `'P'`, Net labels: `'L'`<br>- Auto-connects nets with same name | 🔗 Routing:<br>- Select active layer (e.g., `F.Cu`)<br>- Use `'X'` to route tracks<br>- `'V'` inserts via to switch layers<br>- Pads support multi-layer connections |
| 🔠 Annotate:<br>- Assign reference designators<br>- Fill values<br>- Auto or manual<br><br>🧩 Assign footprints:<br>- Use Footprint Assignment tool<br>- Filters: pin count, type, library | 🧱 Board Setup:<br>- `File → Page Settings…`: set paper size, title block<br>- `File → Board Setup…`:<br>&nbsp;&nbsp;• **Stackup**: define copper/dielectric layers<br>&nbsp;&nbsp;• **Design Rules**: set spacing, track/via sizes<br>&nbsp;&nbsp;• **Net Classes**: group nets by electrical constraints |
| ✅ Run ERC (Electrical Rules Checker):<br>- Detect floating pins, unpowered nets<br>- Add `PWR_FLAG` if needed<br>- Clear all errors before proceeding | 🔁 Importing From Schematic:<br>- Use `Tools → Update PCB from Schematic…` or press `F8`<br>- A preview shows changes to apply<br>- Click `Update PCB` to bring in footprints and nets<br>- This sync must be done manually after schematic edits |
| 📦 Generate BOM:<br>- `Tools → Generate Bill of Materials`<br>- Export to CSV/HTML<br>- Configure fields & format | 🧲 Add copper zones:<br>- `'Add Filled Zone'` tool<br>- Assign net and layer<br>- Fill with `'B'` or `Edit → Fill All Zones`<br>- Useful for GND/VCC planes<br>- Supports thermal reliefs for soldering |
| 🔁 Sync schematic to PCB:<br>- `F8` or `Tools → Update PCB from Schematic`<br>- Update whenever the schematic changes | ✔️ Run DRC (Design Rule Checker):<br>- Detect shorts, clearance issues, unconnected nets<br>- Set severities in `Board Setup → Design Rules`<br>- Ensure zones are refilled before running |
| 🔗 Link between them:<br>- Every symbol must have a valid footprint<br>- Footprints link back to schematic<br>- 3D models referenced in footprints<br>- Use filters for smart assignment | 🧿 3D Viewer:<br>- `View → 3D Viewer`<br>- Inspect model interactively<br>- Most footprints include STEP/VRML 3D models |
| | 🏭 Fabrication outputs:<br>- `File → Plot…`<br>- Export Gerbers: `*.Cu`, `Edge.Cuts`, `*.Mask`, `*.Silkscreen`<br>- Export `Drill Files`<br>- Submit these to your PCB fab |


> 🧠 **Tip:** Work like you’re flipping pages in a notebook: logic on the left, reality on the right. Iterate often. Validate always.  
The full design flow in KiCad relies on a tightly integrated loop between the schematic and PCB. Keeping them in sync and running ERC/DRC checks regularly ensures a clean and manufacturable board.

---

### 🖼️ Visual Examples

| 🧩 Schematic View | 🧿 3D Board View |
|------------------|------------------|
| ![Schematic LED](../../Img/schLED.png) | ![3D Viewer LED](../../Img/3dViewLED.png) |
