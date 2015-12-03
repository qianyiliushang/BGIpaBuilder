##介绍：	
一个基于xcodebuild命令的ipa打包脚本

##环境要求
* xcode7.0

##Install

    chmod +x ipabuilder
    cp ipabuilder /usr/local/bin/

##使用
1、在当前目录下，直接执行

    ipabuilder
2、打包指定目录的工程    

    ipabuilder -p /Users/user/lcg/code/BGUnlockControllerDemo
3、打包指定目录的workspace工程

    ipabuilder -w /Users/user/lcg/code/BGUnlockControllerDemo
4、打包指定bundleId、证书、描述文件，注意这里设置的描述文件是它的UDID
    
    ./ipabuilder -p /Users/user/lcg/code/BGUnlockControllerDemo -b "com.liuchungui.test" -s "iPhone Distribution: xxxxx" -f "888888-7bf6-42af-bd87-b6bf4a720993" -m enterprise
    
更多的使用，请查看下面的Usage。
##Usage： 
当前工程目录下，不需要指定目录，已经在工程中配置好证书和bundleId，不需要任何参数：
	
	ipabuilder    
指定工程目录，编译project    
	
	ipabuilder -p <project directory> [-o <ipa output directory>] [-s <Code Signing Identity>] [-f <Provisioning Profile>] [-m <export method>] [-c <schemename>] [-b <bunlde identifier>]
	
指定工程目录，编译workspace
	
	ipabuilder -w <workspace directory> [-o <ipa output directory>] [-s <Code Signing Identity>] [-f <Provisioning Profile>] [-m <export method>] [-c <schemename>] [-b <bunlde identifier>]

可选参数：  

	-p PATH		project directory，默认当前目录
	-w PATH		workspace directory，默认当前目录
	-o PATH		输出ipa的文件目录，默认当前目录
	-s NAME		签名证书，不给值默认使用工程中的配置
	-f NAME		描述文件名的UDID，不给值默认使用工程中的配置
   	-c NAME     指定scheme名称，默认使用工程项目名作为scheme
   	-m NAME     指定method，现在只有app-store、enterprise、ad-hoc、development、空五种，默认为空
   	-b NAME     指定工程的bundleId
