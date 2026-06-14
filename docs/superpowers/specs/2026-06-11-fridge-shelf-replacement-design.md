# Fridge Door Shelf Replacement — Design Doc

**Date:** 2026-06-11  
**Status:** In progress — awaiting clean LiDAR scan of bin

---

## Problem

One or more door shelf bins on a Frigidaire/Electrolux side-by-side refrigerator have cracked and broken. Goal is to 3D print a functional replacement.

---

## Fridge

- **Model:** LCHX2636TF0 (Canadian label) / LGHX2636TF0 (US equivalent)
- **Make:** Frigidaire by Electrolux Home Products
- **Manufactured:** June 2018 (Mexico)
- **Type:** 26 cu ft side-by-side

---

## Broken Part

The cracked bin is one of the **door shelf bins** on the refrigerator door — clear plastic tray that clips onto horizontal door rails.

**OEM part candidates:**

| Part # | Description | Approx. dimensions | Price |
|--------|-------------|-------------------|-------|
| 242126602 | Lower door shelf bin (clear) | 15-7/8" L × 4-1/2" W × 5-3/4" H (front ~4" H) | ~$33–43 |
| 240356401 | Upper door shelf bin (gallon size) | 15.42" L × 7.1" D × 5.04" H | ~$55 |

OEM parts available on eBay (~$33 shipped) as alternative to printing.

---

## 3D Printing Service

**Port Jefferson Free Library**  
100 Thompson Street, Port Jefferson, NY 11777  
portjefflibrary.org/3Dprinter | 3dprint@portjefflibrary.org

- **Printers:** Bambu X1C (Adult dept), Bambu Lab P1S Combo (Teen dept)
- **Max build volume:** 10" L × 10" W × 10" H (256 × 256 × 256 mm)
- **File format:** 3MF
- **Cost:** $1 per hour
- **Submission:** Email file + print details (color, quantity)

---

## Key Constraint

The bin (~15-7/8" long) **exceeds the 10" max build volume**. It must be printed as **two halves** joined with a locking seam and glued with epoxy or super glue.

---

## Design Plan

### Approach: Model from LiDAR scan + known dimensions

1. **Scan** the broken bin in Scaniverse using Object mode (isolated, on flat table)
2. **Extract dimensions** from OBJ bounding box (units: meters)
3. **Model** a clean replacement in OpenSCAD — parametric, easy to tweak
4. **Split** the model at midpoint with alignment pins for glue-up
5. **Export** as 3MF, submit to library

### Model structure (OpenSCAD)
- Outer shell with rounded front lip (matching original profile)
- Flat bottom with reinforcing ribs
- Back rail clips (exact geometry from scan)
- Split seam at midpoint with male/female alignment pins

---

## Status

- [x] Fridge model identified
- [x] OEM part numbers found
- [x] Library 3D print service details confirmed
- [x] Build volume constraint identified (needs 2-piece split)
- [ ] Clean LiDAR scan of bin (first scan captured too much environment — redo in Object mode)
- [ ] Extract clip/mounting dimensions from scan
- [ ] OpenSCAD model
- [ ] 3MF export
- [ ] Submit to library
