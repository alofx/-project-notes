# Video Resolution Note

**Date:** 2026-04-28
**Status:** REMADE — See updated files

---

## Original Video Resolutions (Before Fix)

| Video | Resolution | Aspect Ratio | Notes |
|-------|-----------|--------------|-------|
| `1st.mp4` (Dirty) | 3836×2160 | 16:9 | ~4K UHD |
| `2nd.mp4` (Foam) | 3524×2352 | ~3:2 | Different resolution |
| `3rd.mp4` (Clean) | 3524×2352 | ~3:2 | Different resolution |

## Issue

The first video is **4K (16:9)** while the other two are **lower resolution with a different aspect ratio (~3:2)**. This caused inconsistent scaling and potential quality loss when combining.

## Fix Applied

All three videos were re-encoded to a consistent **3840×2160 (4K, 16:9)** resolution with proper letterboxing/padding to maintain aspect ratios without stretching.

## Files

| File | Location |
|------|----------|
| Original combined (1080p) | `vice-details/website-assets/hero-scroll-video.mp4` |
| Updated combined (4K) | `vice-details/website-assets/hero-scroll-video-4k.mp4` |
| Copy in ALO SCALE | `Documents/ALO SCALE/hero-scroll-video-4k.mp4` |

---

> **For Kim:** When generating future videos, try to keep all frames at the same resolution and aspect ratio (e.g., 3840×2160 or 1920×1080) for the cleanest results.
