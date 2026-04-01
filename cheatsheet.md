
# Read-write-execute access granting
## Grant your colleague read+execute access to the directory
```setfacl -R -m u:<colleague_username>:rX /mnt/lscratch/users/adhal/scGANDrug```

## Make your parent directory traversable by them too
```setfacl -m u:<colleague_username>:x /mnt/lscratch/users/adhal```

## Verify the ACLs were set correctly
```getfacl /mnt/lscratch/users/adhal/scGANDrug```

# Finding top memoery files
```find /home/users/adhal/ -maxdepth 5 -size +500M -type f 2>/dev/null | xargs du -sh | sort -rh```

# Common Waste Clean-up in HPC
### Clear pip cache (safe to delete)
```pip cache purge```

### Clear conda package cache (keeps envs, removes downloaded tarballs)
```conda clean --all```

### See what conda envs you have and their sizes
```conda info --envs```
