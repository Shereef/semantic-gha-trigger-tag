![image](https://github.com/Shereef/semantic-gha-trigger-tag/assets/356763/6fbd75ac-1a24-4eba-96c5-c5c480a3607c)

I am using the token above

I have also read [this discussion](https://github.com/semantic-release/semantic-release/discussions/1906)

# Solution

`[skip ci]` was being added by `@semantic-release/git`

the solutions is to replace it [like so]([url](https://github.com/Shereef/semantic-gha-trigger-tag/commit/39996f202cf6fa6c3fa14806062c6e2b39e739df)):
```
-    "@semantic-release/git",
+    [
+      "@semantic-release/git",
+      {
+        "message": "chore(release): ${nextRelease.version}\n\n${nextRelease.notes}"
+      }
+    ],
```
