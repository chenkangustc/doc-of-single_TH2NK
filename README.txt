�������cmake���б��룬���ں���������ƣ���ǰ֧��VS+Intel(Win32), VS+Intel(Win64), LINUX64(ifort)����HDF5��Ŀ�ȿ�����Ԥ�ȱ���Ķ������ļ���Ҳ����ֱ�Ӵ�Դ�ļ����б��롣
-->LINUX64:
export FC=ifort
mkdir build & cd build
cmake dir-to-CMakeLists.txt

-->Win:
mkdir build & cd build
cmake -G "platform" dir-to-CMakeLists.txt
ָ����ͬ��Platform�������ɲ�ͬVS�汾�Ĺ����ļ�������platform����ȡ��
Visual Studio 11 2012               : 32λ��VS2012�����ļ�
Visual Studio 11 2012 Win64         : 64λ��VS2012�����ļ�
Visual Studio 12 2013
Visual Studio 12 2013 Win64

================================================================================
����֮������ֶ����������ļ������б��룺
1, ����ϵͳ��ѡ��hdf5-1.8.16-win32-vs2013-shared.zip����hdf5-1.8.16-win64-vs2013-shared.zip������װĿ¼bin��ӵ�path·�����ú�����Ϊ�����������裻
2, ����ϵͳ��ѡ��HDFView-2.11-win32-vs2012.zip����HDFView-2.11-win64-vs2012.zip���ù���Ϊ���ݴ������裻
3, �½������ļ�����/src, /lib-32bit, lib-64bit���õ����̵�.vfprojͬһĿ¼��
4, �򹤳������/src�е�Դ�ļ���
5, ���ù������ԣ�
6, ���뼴�ɣ�

�����������ã�
1, ����Win32ƽ̨�µ�Debug��Release�������ã�
-->Fortran-->General-->Additional Include Directories: .\lib-32bit\mathlib\include; .\lib-32bit\xmlfox\include; .\lib-32bit\hdf5\include; .\lib-32bit\lapack\include; .\lib-32bit\refprop\include;
-->Linker-->General-->Additional Library Directories: .\lib-32bit\mathlib\lib; .\lib-32bit\xmlfox\lib; .\lib-32bit\hdf5\lib; .\lib-32bit\lapack\lib; .\lib-32bit\refprop\lib;
-->Linker-->Input-->Additional Dependencies: mathlib.lib refprop.lib blas.lib lapack.lib fox_common.lib fox_dom.lib fox_fsys.lib fox_sax.lib fox_utils.lib fox_wxml.lib hdf5.lib hdf5_fortran.lib hdf5_hl.lib hdf5_hl_fortran.lib
-->Linker-->Input-->Ignore Specific Library: debug--MSVCRT.lib;
-->Fortran-->Language-->Process OpenMP Directives: /Qopenmp
-->Linker-->System-->Stack Reserve Size: 100000000
2, �½�x64ģʽ��Ȼ�����е�lib-32bit��Ϊ64λ�����ڵ�λ�ã��˴�Ϊlib-64bit

��������.vfproj·���ϲ��е�src_lib�У�·�����÷�ʽΪ��
..\src_lib\lib-32bit\mathlib\include; ..\src_lib\lib-32bit\xmlfox\include; ..\src_lib\lib-32bit\hdf5\include; ..\src_lib\lib-32bit\lapack\include; ..\src_lib\lib-32bit\refprop\include;
..\src_lib\lib-32bit\mathlib\lib; ..\src_lib\lib-32bit\xmlfox\lib; ..\src_lib\lib-32bit\hdf5\lib; ..\src_lib\lib-32bit\lapack\lib; ..\src_lib\lib-32bit\refprop\lib;

˵����
a, HDF5�汾ѡ��1.8.16����Ϊ�ð汾�����ϵĶ������ļ�֧��Fortran 2003�����ǵ�ǰ�������ģ�
��NOTE: ��ý�ԭ����hdf5��ж�ص���ͬʱ���°�װλ�õ�binĿ¼��ӵ���������path�У���D:\Program Files\HDF_Group\HDF5\1.8.16\bin��
b, Ϊ�˷���32λ�Լ�64λϵͳ���ڹ���Ŀ¼�ļ������ṩ��32λ�ĺ����⣨lib-32bit�ļ��У��Լ�64λ�ĺ����⣨lib-64bit�ļ��У���
�������64λ����������Ŀ���̵����ù�������ѡ��x64���������32λ����������Ŀ���̵����ù�������ѡ��Win32��ֱ�ӱ��뼴�ɣ����·�����Ѿ����úá�
