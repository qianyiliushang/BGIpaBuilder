##介绍：	
一个基于xcodebuild命令的ipa打包脚本

##使用说明：
#####当前工程目录下，不需要指定目录，编译project和workspace都使用：
	ipabuilder <schemeName> [-o <ipa output directory>] [-s <Code Signing Identity>] [-m <Provisioning Profile>]
#####指定工程目录，编译project
	ipabuilder <schemeName> -p <project directory> [-o <ipa output directory>] [-s <Code Signing Identity>] [-m <Provisioning Profile>]
#####指定工程目录，编译workspace
	ipabuilder <schemeName> -w <workspace directory> [-o <ipa output directory>] [-s <Code Signing Identity>] [-m <Provisioning Profile>]

#####可选参数：  
	-p PATH		project directory，默认当前目录
	-w PATH		workspace directory，默认当前目录
	-o PATH		输出ipa的文件目录，默认当前目录
	-s NAME		签名证书，不给值默认使用工程中的配置
	-m NAME		描述文件，不给值默认使用工程中的配置
	
##Example
#####不指定目录
```
cd Test
ipabuilder Test
```