

**Övning 1**

1.1) Installation och grundkonfiguration av git
https://git-scm.com/downloads. Om du använder windows rekommenderar jag att du väljer med Git bash

1.2) Verifiera att git är korrekt installerat
```
illidium-q35:~ benc$ git --version
git version 2.11.0 (Apple Git-81)
```
1.3) Registrera en användare på github

---
**Övning 2**
Skapa ett tomt privat repo via Github, hantera filer och status på filer i repot.

2.1) Skapa repo på Github

2.2) klona github repot till din lokala dator

```
illidium-q35:git benc$ cd ~/git/tmp/

illidium-q35:tmp benc$ git clone https://github.com/bennchri/git-training.git


```
2.2) Skapa en fil som heter ovning2.txt och lägg in den i repot. Avsluta editorn/stäng filen i editorn när du är klar ska det se ut så här ungefär:
```
illidium-q35:git-training benc$ tree
.
└── ovning2.txt

0 directories, 1 file
```
Vad är statusen i ditt repo?
```
illidium-q35:git-training benc$ git status
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	ovning2.txt

nothing added to commit but untracked files present (use "git add" to track)
```

2.3) Stagea övning2.txt
```
illidium-q35:git-training benc$ git status
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

	new file:   ovning2.txt
 ```
Vad är statusen i ditt repo?

2.4) Commita övning2.txt till ditt repo
```
illidium-q35:git-training benc$ git commit -m "ovning2 added"
[master (root-commit) 46a9561] ovning2 added
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 ovning2.txt
 ```
Vad är statusen i ditt repo?

---

2.5) Skapa en .gitignore fil med innehållet '*.eee' på första raden. Spara filen i ditt repo och committa den

2.6) Skapa en ny fil i ditt repo med namnet minfil.eee 

2.7) Vad är statusen i ditt repo? Varför?


**Övning 3**
Traversera tidslinjen i git repot

3.1) Editera filen ovning2.txt genom att lägga in en valfri rad med text och spara filen. Avsluta editorn/stäng filen i editorn.
Vad är statusen i ditt repo?
```
illidium-q35:git-training benc$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   ovning2.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
3.2) Kör nödvändiga git kommandon för att få dina ändringar commitade i ditt repo. När du är klar ska statusen i repot se ut så här ungefär
```
illidium-q35:git-training benc$ git status
On branch master
nothing to commit, working tree clean
```
3.3) Lista tidslinjen för commits i ditt repo
```
illidium-q35:git-training benc$ git log
commit 2167d0aec5bc7a3ad39fe2d5fcca484136aebc11
Author: benneth.christiansson <benc@redpill-linpro.com>
Date:   Wed Aug 21 09:31:18 2019 +0200

    ovning2 uppdaterad

commit 46a9561152240f011db8914f293526ff280ffca2
Author: benneth.christiansson <benc@redpill-linpro.com>
Date:   Wed Aug 21 09:24:24 2019 +0200

    ovning2 added
```
3.4) Traversera din tidslinje (checka ut) till din första commit

```
illidium-q35:git-training benc$ git checkout 46a9
Note: checking out '46a9'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b <new-branch-name>

HEAD is now at 46a9561... ovning2 added

```
Vad är innehållet i filen ovning2.txt?
Varför har filen det innehållet?
Avsluta editorn/stäng filen i editorn.

3.5) Avsluta traversering och återställ ditt repo till att kunna ta emot nya commits
```
illidium-q35:git-training benc$ git checkout master
Switched to branch 'master'

illidium-q35:git-training benc$ git status
On branch master
nothing to commit, working tree clean
```

3.6) Editera filen ovning2.txt genom att lägga in ytterligare en valfri rad med text och spara filen.
Vad är statusen i ditt repo nu?

3.7) Traversera din tidslinje till din första commit 
```
illidium-q35:git-training benc$ git checkout 489d
M	ovning2.txt
Note: checking out '489d'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b <new-branch-name>

HEAD is now at 489da81... Updated ovning2
```
Vad är innehållet i filen ovning2.txt?
Varför har filen det innehållet?
Avsluta editorn/stäng filen i editorn.
Är ditt repo i ett detached state just nu?
```
illidium-q35:git-training benc$ git status
HEAD detached at 489da81
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   ovning2.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
3.8) Avsluta traversering och återställ ditt repo till att kunna ta emot nya commits

3.9) Commita dina ändringar i ovning2.txt

3.10) Traversera till din första commit 
Vad är innehållet i filen ovning2.txt? 
Varför?

3.11) Avsluta traversering och återställ ditt repo till att kunna ta emot nya commits


---
**Övning 4**
Genomför några vanliga "ångra" åtgärder

4.1) Editera filen ovning2.txt genom att lägga in ytterligare en valfri rad med text och spara filen. Avsluta editorn/stäng filen i editorn.

4.2) Ångra din editering genom att göra en återställning (reset) till lämplig punkt i repot.
```
illidium-q35:git-training benc$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   ovning2.txt

no changes added to commit (use "git add" and/or "git commit -a")

illidium-q35:git-training benc$ git reset head --hard
HEAD is now at 6936b26 ovning2 updated

illidium-q35:git-training benc$ git status
On branch master
nothing to commit, working tree clean
```

4.3)  Editera filen ovning2.txt genom att lägga in ytterligare en valfri rad med text och spara filen. Avsluta editorn/stäng filen i editorn.

4.4) commita dina ändringar till ditt repo

4.5) Ångra ditt commitmeddelande det borde ha varit "nu är det fixxat
```
illidium-q35:git-training benc$ git log
commit 6936b265dc98d2d55556aa3defdab4df424d53cb
Author: benneth.christiansson <benc@redpill-linpro.com>
Date:   Wed Aug 21 10:36:37 2019 +0200

    ovning2 updated
...

illidium-q35:git-training benc$ git commit --amend -m "nu är det fixxat"
[master 7ed07b1] nu är det fixxat
 Date: Wed Aug 21 10:36:37 2019 +0200
 1 file changed, 1 insertion(+)

illidium-q35:git-training benc$ git log
commit 7ed07b18b9e1b3092eba1161680129583130338a
Author: benneth.christiansson <benc@redpill-linpro.com>
Date:   Wed Aug 21 10:36:37 2019 +0200

    nu är det fixxat
...
```
4.6) Editera filen ovning2.txt genom att lägga in ytterligare en valfri rad med text och spara filen. Avsluta editorn/stäng filen i editorn.

4.7) stagea dina ändringar

4.8) Ångra din stagening
```
illidium-q35:git-training benc$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   ovning2.txt

no changes added to commit (use "git add" and/or "git commit -a")

illidium-q35:git-training benc$ git add .

illidium-q35:git-training benc$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   ovning2.txt

illidium-q35:git-training benc$ git reset head --hard
HEAD is now at 489da81 Updated ovning2 added ovning3

illidium-q35:git-training benc$ git status
On branch master
nothing to commit, working tree clean
```

4.9) Radera dina två senaster commits
```
illidium-q35:git-training benc$ git log
commit 2437bb4f051bde7481f6bd1f74320d1e22212932
Author: benneth.christiansson <benc@redpill-linpro.com>
Date:   Wed Aug 21 11:21:56 2019 +0200

    updated ovning2

commit 489da81cfe9967f5964783f94d62b9a133a8647b
Author: benneth.christiansson <benc@redpill-linpro.com>
Date:   Wed Aug 21 10:13:52 2019 +0200

    Updated ovning2 added ovning3

commit 2167d0aec5bc7a3ad39fe2d5fcca484136aebc11
Author: benneth.christiansson <benc@redpill-linpro.com>
Date:   Wed Aug 21 09:31:18 2019 +0200

    ovning2 uppdaterad

commit 46a9561152240f011db8914f293526ff280ffca2
Author: benneth.christiansson <benc@redpill-linpro.com>
Date:   Wed Aug 21 09:24:24 2019 +0200

    ovning2 added

illidium-q35:git-training benc$ git reset 2167 --hard
HEAD is now at 2167d0a ovning2 uppdaterad
illidium-q35:git-training benc$ git log
commit 2167d0aec5bc7a3ad39fe2d5fcca484136aebc11
Author: benneth.christiansson <benc@redpill-linpro.com>
Date:   Wed Aug 21 09:31:18 2019 +0200

    ovning2 uppdaterad

commit 46a9561152240f011db8914f293526ff280ffca2
Author: benneth.christiansson <benc@redpill-linpro.com>
Date:   Wed Aug 21 09:24:24 2019 +0200

    ovning2 added
```

---
**Övning 5**
Synka ditt remote repo

5.3) Lägg till en fil i repot och commita den lokalt.

5.4) Synka ditt lokala repo med github (push)

5.5) Verifiera att filen är på plats i ditt github repo.

5.6) Uppdatera filen direkt på github och commita den direkt på github
Hur är relationen mellan ditt lokala repository och github är någon framför/efter i tidslinjen?

5.7) Synka github med ditt lokala repo(pull)
Vad är innehållet i filen nu?
Varför?

5.8) Editera filen lokalt genom att lägga in ytterligare en valfri rad med text och spara filen. Avsluta editorn/stäng filen i editorn. commita dina ändringar lokalt.

5.9 Uppdatera filen direkt på github och commita den direkt på github
Hur är relationen mellan ditt lokala repository och github är någon framför/efter i tidslinjen?

5.10 Lös synkproblemen (merge)

5.11 Be en kollega bjuda in dig till sitt github repo

5.12 klona kollegans repo lokalt på din dator
På hur många ställen finns nu kollegans repo?

5.13 Skapa ytterligare ett tomt repo på github

5.14 Koppla ihop ddet lokala repot du gjorde i övning 1 med ditt nya github repo

5.15 synka ditt lokala repo med github (push)

---
**Övning 6**
readme, wiki och markdown

6.1 Skapa en enkel markdown wiki via Readme (https://guides.github.com/features/mastering-markdown/) i något av dina github repon

6.2 Synka ändringarna till ditt lokala repo.

6.3 Uppdatera wikin lokalt på din dator med valfri editor och commita dem lokalt

6.4 Synka ditt lokala repo med github

6.5 Uppdatera wikin direkt på github och commita direkt på github

6.6 Synka github med ditt lokala repo.

---
