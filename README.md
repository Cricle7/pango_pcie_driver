
```
sudo apt update
sudo apt install linux-headers-$(uname -r)
```
```
module_test.c
    ├── 模块安装函数xxx
    │   └── 注册字符设备驱动register_chrdev(MYNMAJOR, MYNAME, &test_module_fops)
    ├── 模块安装函数yyy
    │   └── 注销字符设备驱动unregister_chrdev(MYNMAJOR, MYNAME)
    │   
    ├── module_init(模块安装函数xxx);
    ├── module_exit(模块卸载函数yyy);
    │     
    └── MODULE_LICENSE("GPL");
```