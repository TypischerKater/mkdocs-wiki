---
tags:
  - computer
---

# Format a Hard Drive & Delete Recovery Partitions

Open powershell with admin rights and type
```bash
diskpart
```

Then list the available disks
```bash
list disk
```

Select the disk you want to clean for example for disk 1
```bash
select disk 1
```

Clean the disk 
```bash
clean
```

Then go to disk manager and initilaze with gpt