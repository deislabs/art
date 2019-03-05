# Diffing Sketch Files

1. Add the following line to your **~/.bash-profile**
    ```
    export PATH=$PATH:"$(mdfind kMDItemCFBundleIdentifier == 'com.bohemiancoding.sketch3' | head -n 1)/Contents/Resources/sketchtool/bin/"
    ```
1. Add the following lines to your **~/.gitconfig**
    ```
    [diff "sketchtool"]
      textconv = "sketchtool dump"
      cachetextconv = true
      binary = true
   ```

Now when a sketch file is modified, you can see a text representation of the change:

```diff
$ git diff
diff --git a/porter/porter-logo.sketch b/porter/porter-logo.sketch
index b38789b..1842779 100644
--- a/porter/porter-logo.sketch
+++ b/porter/porter-logo.sketch
@@ -88093,7 +88093,7 @@
                 "objectID" : "39D3F54C-F4E0-418A-A723-2038D25BC17E",
                 "width" : 668.45000000000005,
                 "x" : 676,
-                "y" : 344
+                "y" : 500
               },
```