# Installing and Upgrading KiCad

## 🧰  Install KiCad from the Official PPA (Stable Version)

This is the recommended method to install the latest stable version of KiCad directly from the official developers on Ubuntu.

### 📋 Steps:

1. **Open a terminal**  
   You can do this by pressing `Ctrl + Alt + T`.

2. **Add the KiCad PPA repository**:
   ```bash
   sudo add-apt-repository --yes ppa:kicad/kicad-9.0-releases
   sudo apt update
   sudo apt install --install-recommends kicad
   
   ```
Older stable releases of KiCad are available in other similarly-named PPAs. To see the complete list of available PPAs, we need to check the KiCad Launchpad page.

---

### 🔄 Migrating from Previous KiCad Versions

To migrate a project to a newer KiCad version, simply open and save the schematic and PCB files.  
⚠️ **Important:** Always back up your project first — once saved, it won't open in older versions.  
Symbol libraries from versions before 6.0 must be converted to the new format to be editable.

---

### 📘 Basic Terminology (KiCad)

KiCad uses standard EDA (Electronics design automation) terms along with some tool-specific ones:

- **Schematic**: A single-page circuit diagram; multiple sheets form a **hierarchical schematic** with one root sheet.
- **Symbol**: Represents circuit elements (e.g. resistors, power rails) placed in schematics; defined by pins and stored in symbol libraries.
- **Netlist**: Describes electrical connections between symbol pins; used internally between schematic and PCB editors.
- **PCB (Printed Circuit Board)**: The physical design derived from the schematic/netlist.
- **Footprint**: A layout representation of a component placed on the PCB; connects to symbol pins via pads.
- **Worksheet**: A drawing template with a title block used in schematics and PCB documentation.
- **Plotting**: The process of generating outputs (e.g. Gerber, PDF) for manufacturing or review.
- **Ngspice**: An integrated circuit simulator for analyzing schematic behavior.

> These terms are foundational for navigating KiCad’s tools and workflow.

---

### 🧩 KiCad Components Overview

KiCad is made up of several integrated and standalone tools that support the PCB design workflow.  
Older versions required manual netlist transfers between the schematic and PCB editors.  
Modern versions integrate these tools through a unified project manager, streamlining the process.

> Always check which KiCad version a tutorial references, as workflows may differ.

---

### 📚 Main KiCad Tools

| **Component Name**       | **Description**                                                                 |
|--------------------------|---------------------------------------------------------------------------------|
| Schematic Editor         | Create and edit schematics; simulate with SPICE; generate BOM files             |
| Symbol Editor            | Create and edit schematic symbols; manage symbol libraries                      |
| PCB Editor               | Create and edit PCBs; export 2D/3D; generate fabrication outputs                |
| Footprint Editor         | Create and manage PCB footprints and libraries                                 |
| GerbView                 | Viewer for Gerber and drill files                                              |
| Bitmap2Component         | Convert bitmap images into symbols or footprints                               |
| PCB Calculator           | Calculate values like track width, spacing, color codes, etc.                  |
| Page Layout Editor       | Create and edit worksheet templates                                            |

---

### 🖱️ KiCad User Interface Overview

KiCad editors share common UI behavior:

- **Selection**: Click or drag to select objects.  
  - Left-to-right drag: selects fully enclosed items.  
  - Right-to-left drag: selects any intersecting items.  
  - Modifier keys change selection behavior (platform-specific; see Preferences > Editing Options).

- **Tools**: Editors work in tool modes (e.g., selection, placement, inspection).  
  - The **active tool** is highlighted in the toolbar and shown in the status bar.  
  - **Esc** cancels current actions. Pressing **Esc twice** returns to the selection tool.

> The default tool is selection mode. User interactions vary slightly by platform.

---

📖 For more detailed information, visit the official documentation:  
[https://docs.kicad.org/](https://docs.kicad.org/)