### Centos U盘安装记录

1. ultroIso进行iso文件的写入；

2. 创建引导文件，引导文件在u盘中，isolinux下;

3. 修改bios进行u盘的启动；

4. 进入linux的安装后，按e进入centos的详细安装界面；

5. 编辑:

> vmlinuz initrd=initrd.img inst.stage2=hd:LABEL=CentOS\x207\x20x86_64 rd.live.check quiet
 
修改为：

> vmlinuz initrd=initrd.img inst.stage2=hd:/dev/sdb4 quiet 

这里需要注意/dev/sdb4可能不是你的u盘位置，可以通过修改: 

> vmlinuz initrd=initrd.img inst.stage2=hd:LABEL=CentOS\x207\x20x86_64 rd.live.check quiet

修改为：

> vmlinuz initrd=initrd.img linux dd quiet

    改好之后回车，然后查看设备列表，

6.ctrl+x 启动

7.安装iso需要copy一份进入u盘中；
