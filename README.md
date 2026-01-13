# Deepdroid #
The android13 repo tree is now private!!!

# Based #
[Pixel Experience - Android13](https://github.com/PixelExperience/manifest/tree/thirteen/)

### Sync ###

```bash

# Initialize local repository
repo init -u https://github.com/doanvtamhuynh/Deepdroid_manifest -b thirteen

# Sync
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

### Build ###

```bash

# Set up environment
$ . build/envsetup.sh

# Choose a target
$ lunch aosp_$device-userdebug

# Build the code
$ mka bacon -jX
```

### Update user build ###

```
project build/make/
diff --git a/core/version_defaults.mk b/core/version_defaults.mk
index 711e7702a..35562dd3a 100644
--- a/core/version_defaults.mk
+++ b/core/version_defaults.mk
@@ -103,7 +103,7 @@ ifndef PLATFORM_SECURITY_PATCH
     #  It must be of the form "YYYY-MM-DD" on production devices.
     #  It must match one of the Android Security Patch Level strings of the Public Security Bulletins.
     #  If there is no $PLATFORM_SECURITY_PATCH set, keep it empty.
-    PLATFORM_SECURITY_PATCH := 2024-01-05
+    PLATFORM_SECURITY_PATCH := 2025-10-05
 endif
 
 include $(BUILD_SYSTEM)/version_util.mk
diff --git a/tools/releasetools/edify_generator.py b/tools/releasetools/edify_generator.py
index c80becfac..d4727b40d 100644
--- a/tools/releasetools/edify_generator.py
+++ b/tools/releasetools/edify_generator.py
@@ -268,11 +268,11 @@ class EdifyGenerator(object):
                                   security_patch, device):
     self.Print("----------------------------------------------")
     if is_plus:
-      self.Print("        PixelExperience (Plus edition)")
-      self.Print("                by jhenrique09")
+      self.Print("                   DeepDroid")
+      self.Print("                by doanvtamhuynh")
     else:
-      self.Print("              PixelExperience")
-      self.Print("              by jhenrique09")
+      self.Print("                 DeepDroid")
+      self.Print("              by doanvtamhuynh")
     self.Print("----------------------------------------------")
     self.Print(" Android version: %s"%(android_version))
     self.Print(" Build id: %s"%(build_id))
```