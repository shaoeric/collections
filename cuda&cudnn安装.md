#### cuda安装
1. 准备文件
	- cuda-repo-ubuntu16.04-10.0_local_xxx_amd64.deb
	- cudnn-10.0-linux-x64-v7.4.1.5

2. 安装cuda
	- 安装cuda
        ```shell
        sudo dpkg -i cuda-xxx.deb
        ```
	     
	- 安装key
		
		```shell
		sudo apt-key add /var/cuda-xxx.pub
		```
	- 更新
	
		```shell
		sudo apt update
		```
	
	- 安装
		```shell
		sudo apt-get install cuda
		```
3. 将cuda添加到环境变量中
	```
	vi .bashrc
	```
	```
	export PATH="/usr/local/cuda/bin:$PATH"
	export LD_LIBRARY_PATH="/usr/local/cuda/lib64:$LD_LIBRARY_PATH"
	```
	```
	source ~/.bashrc
	```
4. 完成[安装完成后，会自动把显卡驱动安装好]

#### cudnn
**cudnn要与cuda版本相匹配** cuda10.0<=>cudnn7.4.1
1. 切换到cudnn.tgz压缩包路径
2. 解压cudnn文件，生成一个cuda文件夹
3. 进入到cuda文件夹
4. 把cudnn文件拷贝到已经安装的cuda/include目录下
	```
	sudo cp include/cudnn.h /usr/local/cuda/include/
	sudo cp lib64/libcudnn* /usr/local/cuda/lib64/
	```
5. 设置环境变量，指定cudnn的位置
	```
	export LD_LIBRARY_PATH="/usr/local/cuda/lib64:$LD_LIBRARY_PATH"
	```
	```
	source ~/.bashrc
	```