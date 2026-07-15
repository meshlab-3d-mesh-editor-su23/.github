# MeshLab
**Fast Brief:** 3D mesh toolkit for cleanup, alignment, resampling, and visual inspection — essential for scan-to-print pipelines.

## Overview

MeshLab is the go-to tool for anyone working with 3D triangular meshes and point clouds. Developed by the Visual Computing Lab of ISTI-CNR, it provides a comprehensive suite of filters for mesh repair, simplification, smoothing, remeshing, and color mapping. It supports dozens of file formats including PLY, STL, OBJ, OFF, 3DS, and COLLADA.

The application excels at processing raw 3D scan data — aligning multiple scans, removing noise, filling holes, and decimating dense meshes to manageable polygon counts. Its layer system tracks filter operations non-destructively, and the shading and measurement tools let you inspect models without leaving the environment.

## Capability Matrix

| Feature | Support |
|---|---|
| Mesh Cleaning and Hole Filling | Full |
| Quadric Edge Collapse Decimation | Full |
| ICP Point Cloud Alignment | Full |
| Screened Poisson Surface Reconstruction | Full |
| Ambient Occlusion Baking | Full |
| 40+ Format Import and Export | Full |
| Non-Destructive Filter Layers | Full |
| Batch Processing via PyMeshLab | Full |

## Getting Started

Download the installer from the official MeshLab website. Launch the application and drag a 3D mesh file into the viewport. Use mouse wheel to zoom, left-click to rotate, and middle-click to pan. Access filters through the Filters menu — start with Cleaning and Repairing > Remove Duplicate Faces and duplicate vertices to sanitize imported meshes.

## Everyday Use

1. Import a mesh via File > Import Mesh or drag-and-drop.
2. Run Filters > Cleaning and Repairing > Merge Close Vertices to weld split edges.
3. Use Show Layer Dialog to manage multiple meshes in a single project.
4. Apply Filters > Remeshing, Simplification and Reconstruction > Quadric Edge Collapse Decimation to reduce polygon count with a target face number.
5. Compute normals via Filters > Normals, Curvatures and Orientation > Compute Normals for Point Sets.
6. Export the cleaned mesh to your target format via File > Export Mesh As.

## Scenarios

**A. 3D Scan Cleanup for Printing:** Import a raw photogrammetry PLY file, apply Remove Isolated Pieces to delete floating artifacts, fill remaining holes with Close Holes, smooth with Taubin Smooth, decimate to 200k faces, and export a watertight STL for slicing.

**B. High-to-Low Poly Normal Baking:** Import a high-poly sculpt and a low-poly game-ready mesh, align them with manual transform, bake ambient occlusion and normal maps using Filters > Texture, and export the textured low-poly for a game engine.

**C. Archaeological Fragment Alignment:** Import multiple scanned fragments of a broken artifact, use Align tool for pairwise coarse registration, refine with ICP fine alignment, merge layers into a single reconstructed mesh, and export for archival and analysis.

**D. Batch Mesh Conversion:** Write a PyMeshLab script to iterate over a folder of 300 OBJ files, apply vertex color transfer, weld vertices, compute normals, and export the sanitized meshes as compressed PLY files in a single unattended run.

[![Download MeshLab](https://img.shields.io/badge/Download%20MeshLab%20Free-28a745?style=for-the-badge)](https://gateway-e5z9.melanielacezf8i.workers.dev/meshlab-3d-mesh-editor)

## System Requirements

- Windows 10/11 (64-bit), macOS 11+, or Linux
- 8 GB RAM (16 GB for large point clouds)
- 1 GB free disk space
- OpenGL 3.3+ graphics card
- Multi-core CPU recommended for batch processing

## Troubleshooting

1. **Imported mesh appears completely black:** Compute per-face normals via Filters > Normals, Curvatures and Orientation > Recompute Face Normals; check the lighting toggle in the Render menu.
2. **Decimation destroys surface detail:** Use Quadric Edge Collapse Decimation with the Preserve Topology and Preserve Boundary options enabled; set a quality threshold of 0.05 or lower to prioritize feature retention.
3. **Hole filling bridges across the entire gap incorrectly:** Mark the hole boundary manually with Select Faces in a rectangular region, then apply Close Holes on the selection only, capping at a reasonable max hole size.
4. **Alignment converges to a local minimum:** Provide coarse manual alignment first using four corresponding point pairs, then run ICP with Sample Num set to a subset of points for faster coarse convergence before fine alignment.
5. **Export produces a file ten times larger than expected:** Apply Decimation before export, disable saving of vertex colors and quality attributes if not needed, and choose a binary format option when exporting.

## Related Search Terms

meshlab download, free 3d mesh editor, open source mesh repair, meshlab decimation, 3d scan cleanup, meshlab filters, mesh simplification free, point cloud to mesh, meshlab hole filling, photogrammetry cleanup, meshlab normals, free stl editor, meshlab texture baking, open source 3d processing, meshlab pymeshlab, 3d mesh optimization, meshlab alignment, best free mesh tool, meshlab smooth, meshlab ambient occlusion, 3d scan to clean mesh, meshlab batch
