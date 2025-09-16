# Task 1 — Git Object Model Exploration

## Blob

**Command:**
```
git cat-file -p d800886d9c86731ae5c4a62b0b77c437015e00d2
```

**Output:**
```
123
```

**Description:**  
A blob is an object that stores the content of a file. In this case, it stores the content of `text.txt`.

---

## Tree

**Command:**
```
git cat-file -p 48970b9c6f9b7db827089ec2a429e2627912d762
```

**Output:**
```
100644 blob b1f8af089a94f160ce00ed7710f07a7e9ba6c584    lab1.md
100644 blob 1468ba02d6bcacd3fee5fd378cc02717a8cb2fbc    lab2.md
100644 blob d800886d9c86731ae5c4a62b0b77c437015e00d2    text.txt
```

**Description:**  
A tree is an object that stores a list of files and directories (their blob and tree references). In our example, the tree stores files inside the `labs` folder and points to their blobs.

---

## Commit

**Command:**
```
git cat-file -p a258a2f
```

**Output:**
```
tree 88d87e56d7e3ad0064d3654e0e03035a718be458
parent fe7b4151d42d2e558d6a5a480fdc1ecb88c7e824
author spiriton <i.ershov@innopolis.university> 1757987099 +0300
committer spiriton <i.ershov@innopolis.university> 1757987099 +0300
gpgsig -----BEGIN SSH SIGNATURE-----
 U1NIU0lHAAAAAQAAADMAAAALc3NoLWVkMjU1MTkAAAAgV2Ts47r8/wWn+zLpM99qSDPbpH
 fAoXAdqbhalJYr53UAAAADZ2l0AAAAAAAAAAZzaGE1MTIAAABTAAAAC3NzaC1lZDI1NTE5
 AAAAQCLPtVn51xsb4rz0ZIZWcUU4JVZCAfYtRCQwH4AysLFql+6Cjr5UbQREKXn7gWBpad
 E2UsmeHOGXINXQmXLxFgg=
 -----END SSH SIGNATURE-----

feat: add text.txt
```

**Description:**  
A commit is an object that points to a tree (the state of files), references a parent commit, and stores author, committer, and message information. In this case, the commit records the addition of text.txt to the repository.