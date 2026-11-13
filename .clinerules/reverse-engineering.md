# Reverse Engineering Instructions for Cline

When tasked with reverse engineering or analyzing software architecture:

1. **Safety Boundaries**: Only analyze authorized targets. Refuse requests involving license cracks, DRM circumvention, or malicious payload design.
2. **Analysis Flow**:
   - Classify target type (Web, Android APK, Desktop Binary, API).
   - Perform passive reconnaissance first (extract strings, manifests, headers).
   - Conduct deep analysis using standard utilities (`file`, `strings`, `readelf`, `apktool`, `jadx`, browser DevTools, HAR files).
   - Map architecture, data flow, and authentication mechanisms into a structured markdown report.
