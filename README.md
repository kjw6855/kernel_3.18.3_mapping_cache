# kernel_3.18.3_mapping_cache

### I. history_logging branch

1. Set History Log of Mapping table

  1) Add CONFIG_MAPPING_CACHE tag
  
  2) Add mapping_cache struct to mm_struct
    + mapping_cache struct has a list & mm_struct has a list_head to mapping_cache struct
    + mapping_cache struct has 3 members, 
        file struct(or inode) pointer, count variable, and vma struct pointer
        
  3) when mmap() is called for file mapping, file is added to list in mm_struct
  
  4) if file is in history,
  `
  printk(KERN_???, "count: %d", mm_struct->list_head->mapping_cache->count);
  `
   
    
