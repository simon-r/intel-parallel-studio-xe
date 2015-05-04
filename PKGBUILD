# Contributor: simone riva: siomone.rva -a- gmail com
# Intel Parallel Studio XE 2011 for Linux - ( Intel compiler icc suite )
##########################################################################
# this PKGBUILD splits the main Parallel Studio XE packege in 8 sub-packages:
#
# intel-compiler-base:          Intel C/C++ compiler and base libs
# intel-fortran-compiler:       Intel fortran compiler and base libs"
# intel-openmp:                 Intel OpenMP Library
# intel-idb:                    Intel C/C++ debugger
# intel-ipp:                    Intel Integrated Performance Primitives
# intel-mkl:                    Intel Math Kernel Library (Intel® MKL)
# intel-sourcechecker:          Intel Source Checker
# intel-tbb:                    Intel Threading Building Blocks (TBB)
###########################################################################

# Parallel Studio XE
#     Copyright (C) 2011   Simone Riva
# 
#     This program is free software: you can redistribute it and/or modify
#     it under the terms of the GNU General Public License as published by
#     the Free Software Foundation, either version 3 of the License, or
#     (at your option) any later version.
# 
#     This program is distributed in the hope that it will be useful,
#     but WITHOUT ANY WARRANTY; without even the implied warranty of
#     MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#     GNU General Public License for more details.
# 
#     You should have received a copy of the GNU General Public License
#    along with this program.  If not, see <http://www.gnu.org/licenses/>.

# http://registrationcenter-download.intel.com/akdlm/irc_nas/4992/parallel_studio_xe_2015_update1.tgz

pkgbase="intel-parallel-studio-xe"
#pkgname="intel-parallel-studio-xe"
#pkgname=( 'intel-compiler-base'  'intel-advisor-xe' )
pkgname=('intel-compiler-base' 'intel-openmp' 'intel-fortran-compiler' 'intel-ipp' 'intel-mkl' 'intel-sourcechecker' 'intel-tbb' 'intel-vtune-amplifier-xe' 'intel-inspector-xe' 'intel-advisor-xe' )
#true && pkgname=('intel-compiler-base'  'intel-gdb'  )

PKGEXT='.pkg.tar.gz'

########################################
#OPTIONS begin
# if you are using an AMD 64 cpu set this variable to true, leave it to false if you use an ia32, amd32 or intel64
#_amd_64=false 

# set to true if you want to remove documentations and examples form the packages.
_remove_docs=true

########################################
########################################
# set to true if you want to remove the static objects form the libs .
_remove_static_objects_mkl=true
_remove_static_objects_ipp=true
########################################

_year='2015'
_v_a='3'
_v_b='187'

_update='update3'

pkgrel=1

_sp=''

_icc_ver='15.0.2'
_ipp_ver='8.2.1'
_mkl_ver='11.2.2'
_openmp_ver='15.0.1'
_sourcechecker_ver='15.0.2'
_vtune_ver='3.0.403110'
_advisor_ver='1.10.380555'
_inspector_ver='1.2.379161'

_tbb_ver='4.3.0'


pkgver=${_year}.${_icc_ver}.${_v_a}.${_v_b}

_dir_nr='7538'

options=(strip libtool staticlibs)


#if $_amd_64 ; then
#  _not_arch_64='intel64'
#else
#  _not_arch_64='ia64' 
#fi


url="http://software.intel.com/en-us/articles/non-commercial-software-download/"
arch=('i686' 'x86_64')
license=('custom')
makedepends=('libarchive' 'sed' 'gzip')

_parallel_studio_xe_dir="parallel_studio_xe${_year:+_${_year}}${_sp:+_${_sp}}${_update:+_${_update}}"

source=(
	"http://registrationcenter-download.intel.com/akdlm/irc_nas/${_dir_nr}/${_parallel_studio_xe_dir}.tgz"
	'intel_compilers.sh'
	'intel_vtune-amplifier-xe.sh'
	'intel_advisor-xe.sh'
	'intel_inspector-xe.sh'
	'intel-composer.install'
	'intel-compiler-base.conf' 
	'intel-fortran.conf'
	'intel-openmp.conf'
	'intel-mkl.conf' 
	#'intel-gdb.conf'
	'intel-ipp.conf'
	'intel-tbb.conf'
	'intel-mkl.sh'
        'intel-mkl.install'
        'intel-mkl-th.conf'
	'intel-tbb.install'
	'EULA.txt'
	)





sha256sums=(
	'ab7169989c87bbb0fe66221cb7eb3a26b17c8b9ceff38f1926e5607834306896' # parallel_studio_xe_2015_update3.tgz
	'338041f924d8f3ac31d349bca57f8ab66f094a5bb53d4f821f48fa710a112111' # intel_compilers.sh
	'7da22140b9d8277d06d88f6bd37cb77ed17bc87d4f7ec5958587416639955991' # intel_vtune-amplifier-xe.sh
	'292a9eea2c9a836ee9dc0d4ff28fc741d5548a3182e4f75aec7b93e1dd7b4f21' # intel_advisor-xe.sh
	'6dc3992ac649f979328d13cb98ead95121752a34fbad07d41ee65b084cdf03cf' # intel_inspector-xe.sh
	'3f96dec03111e69d16bb363acf4d0570e8a9526c09e5e542a7558f1b26d043ef' # intel-composer.install
	'31ac4d0f30a93fe6393f48cb13761d7d1ce9719708c76a377193d96416bed884' # intel-compiler-base.conf
	'c165386ba33b25453d4f5486b7fefcdba7d31e156ad280cbdfa13ed924b01bef' # intel-fortran.conf
	'99cc9683cc75934cc21bb5a09f6ad83365ee48712719bfd914de9444695eed13' # intel-openmp.conf
	'a856326362e9b80c19dc237cbf66bf3d96a69bd7ad1baff99ec9849f8208348c' # intel-mkl.conf
	'da6f41c2e002c9a793c75a18c8d1c85ef7ef5bf83a7a0a158ff144481491aac8' # intel-ipp.conf
	'aee2ae7f87f12f4af38d52423b40d547fd5bbe77e18694b9847e9f2a96d33c6e' # intel-tbb.conf
	'5e68c529c65cac54218026c869e54b2ddb268179725fc1e6b56d920470dad999' # intel-mkl.sh
	'11398c0ae2e2011902b1d6356d916d41bb8b54d39d090c6c83630f4b0e84e93a' # intel-mkl.install
	'e515cb28bf40cdb0db818db6a2688a0028575153a1b9d5acfb0bc5f13fe45722' # intel-mkl-th.conf
	'8c6a1f7b1b12d498e68b3085d8b2fcd050505209b7c0f2b870ba5f65ee135a90' # intel-tbb.install
	'228ac25e147adb9b872e1a562e522d2fd48809ccae89b765112009896a6d55a5' # EULA.txt
	)


#_archive=l_ccompxe${_comp}_p_${pkgver}
if [ "$CARCH" = "i686" ]; then
    _i_arch='ia32'
    _i_arch2='i486'

    _not_arch='intel64'
    _not_arch2='x86_64'
else
    _i_arch='intel64' 
    _i_arch2='x86_64'

    _not_arch='ia32' 
    _not_arch2='i486'
fi


 #_parallel_studio_xe_dir="parallel_studio_xe_${_year}_${_sp}_${_update}"         
#source=("http://registrationcenter-download.intel.com/akdlm/irc_nas/${_dir_nr}/${_parallel_studio_xe_dir}.tgz" ${source[@]})


extract_rpms() {
  cd $2
  for rpm_file in ${rpm_dir}/$1 ; do
    echo -e "    Extracting: ${rpm_file}"
    bsdtar -xf ${rpm_file} 
  done
}

set_build_vars() {
  _pkg_ver=${_year}.${_icc_ver}.${_v_a}.${_v_b}
  _composer_xe_dir="composer_xe_${_year}.${_v_a}.${_v_b}"
  rpm_dir=${srcdir}/${_parallel_studio_xe_dir}/rpm
  xe_build_dir=${srcdir}/cxe_build
  base_dir=${srcdir}/..
  _man_dir=${xe_build_dir}/usr/share/man/man1
}


build() {

	set_build_vars

	echo -e "-----------------------------------------------------------------------------"
	echo -e " This PKGBUILD splits the main \e[1mParallel Studio XE\e[0m package in 8 sub-packages:"
	echo -e ""
	echo -e " \e[1mintel-compiler-base:\e[0m          Intel C/C++ compiler and base libs"
	echo -e " \e[1mintel-fortran-compiler:\e[0m       Intel fortran compiler and base libs"
	echo -e " \e[1mintel-openmp:\e[0m                 Intel OpenMP Library"
	echo -e " \e[1mintel-idb:\e[0m                    Intel C/C++ debugger"
	echo -e " \e[1mintel-ipp:\e[0m                    Intel Integrated Performance Primitives"
	echo -e " \e[1mintel-mkl:\e[0m                    Intel Math Kernel Library (Intel® MKL)"
	echo -e " \e[1mintel-sourcechecker:\e[0m          Intel Source Checker"
	echo -e " \e[1mintel-tbb:\e[0m                    Intel Threading Building Blocks (TBB)"
	echo -e "-----------------------------------------------------------------------------"
	echo -e "" 
	echo -e "-----------------------------------------------------------------------------"
	echo -e "For having a minimal working environment you must install the packages:"
	echo -e " intel-compiler-base       intel-openmp "
	echo -e "-----------------------------------------------------------------------------"
	echo -e "" 
	echo -e "-----------------------------------------------------------------------------"
	echo -e "\e[1mWIKI: \e[0m https://wiki.archlinux.org/index.php/Intel_C%2B%2B"
	echo -e "-----------------------------------------------------------------------------"
	echo -e "" 
	echo -e "-----------------------------------------------------------------------------"
	echo -e "\e[1mGithub: \e[0m https://github.com/simon-r/intel-parallel-studio-xe" 
	echo -e "-----------------------------------------------------------------------------"

	echo ${xe_build_dir}

	#  clean the builds dirs
	if [ -d ${srcdir}/opt ] ; then
	  rm -rf ${srcdir}/opt
	fi

	if [ -d ${srcdir}/etc ] ; then
	  rm -rf ${srcdir}/etc
	fi

	if [ -d ${srcdir}/usr ] ; then
	  rm -rf ${srcdir}/usr
	fi
  
	if [ -d ${xe_build_dir} ] ; then 
	  rm -rf ${xe_build_dir}
	fi

	echo ${srcdir}

	mkdir -p ${xe_build_dir}

	# START !
	cd ${xe_build_dir}
	mkdir -p ${xe_build_dir}/etc/profile.d

	if [ "$CARCH" = "i686" ]; then
	  sed 's/<arch>/ia32/' < ${srcdir}/intel_compilers.sh > ${xe_build_dir}/etc/profile.d/intel_compilers.sh
	else
	  sed 's/<arch>/intel64/' < ${srcdir}/intel_compilers.sh > ${xe_build_dir}/etc/profile.d/intel_compilers.sh
	fi

	#sed -i 's/<tbb_arch>/cc4\.1\.0_libc2\.4_kernel2\.6\.16\.21/' ${xe_build_dir}/etc/profile.d/intel_compilers.sh

	chmod a+x ${xe_build_dir}/etc/profile.d/intel_compilers.sh

	mkdir -p ${xe_build_dir}/etc/ld.so.conf.d

	_cnt=0
	for files in ${base_dir}/*.lic ; do
	  _lic_file[_cnt]=${files}
	  _cnt=$(($_cnt+1))
	done


    echo -e ""
	echo -e "-----------------------------------------------------------------------------------"
	mkdir -p ${xe_build_dir}/opt/intel/licenses
    if [ -f "${_lic_file[0]}" ]; then
	    cp ${base_dir}/*.lic ${xe_build_dir}/opt/intel/licenses
	    echo -e "\e[1mFound license files in ${base_dir}."
        echo -e "These will be installed into /opt/intel/licenses ...\e[0m"
    else
	    echo -e "\e[1mNo license files found in ${base_dir}."
        echo -e "Remember to place license files in one of these locations:"
        echo -e "    /opt/intel/licenses"
        echo -e "    ~/intel/licenses"
        echo -e "Or the compiler will not work!\e[0m"
    fi
	echo -e "-----------------------------------------------------------------------------------"
    echo -e ""

	cp ${srcdir}/${_parallel_studio_xe_dir}/license.txt ${xe_build_dir}/opt/intel/license.txt
	
	echo -e ""
	echo -e "-----------------------------------------------------------------------------------"
	echo -e "\e[1mIMPORTANT - READ BEFORE COPYING, INSTALLING, OR USING.\e[0m"
	echo -e ""
	echo -e "Do not copy, install, or use the \"Materials\" provided under this license agreement (\"Agreement\"), until you"
	echo -e "have carefully read the following terms and conditions."
	echo -e ""
	echo -e "By copying, installing, or otherwise using the Materials, you agree to be bound by the terms of this" 
	echo -e "Agreement. If you do not agree to the terms of this Agreement, do not copy, install, or use the Materials."
	echo -e " - A copy of the EULA has been copied in the PKGBUILD directory; plase read carefully the terms and "
	echo -e " - conditions of the Intel license before installing the packages. "
	echo -e "-----------------------------------------------------------------------------------"
	echo -e ""
	echo -e "-----------------------------------------------------------------------------------"
	echo -e " ATTENTION: This PKGBUILD may need up to 20 minutes if you use XZ as a compressor!"
	echo -e "    - The build of the packages: intel-mkl and intel-ipp is particularly slow - "
	echo -e "-----------------------------------------------------------------------------------"
	echo -e ""
	echo -e ""
	echo -e "-----------------------------------------------------------------------------------"
	echo -e " \e[1m\e[5mATTENTION: \e[0m \e[1m\e[31mThis PKGBUILD works with yaourt, "
    echo -e "but consumes a lot of RAM! \e[0m "
	echo -e " Using the makepkg command for building this package is recommended."
	echo -e "-----------------------------------------------------------------------------------"
	echo -e ""
	echo -e ""
	echo -e "-----------------------------------------------------------------------------------"
	echo -e "\e[1m #################### \e[0m"
	echo -e "\e[1m ##### Options: ##### \e[0m"
	if  ${_remove_docs} ; then
	  echo -e " Remove Documentation: YES "
	else
	  echo -e " Remove Documentation: NO "
	fi

	if  ${_remove_static_objects_mkl} ; then
	  echo -e ""
	  echo -e "\e[1m Remove Static Objects from MKL: YES \e[0m \e[1m\e[5m\e[31m ATTENTION !!!! \e[0m "
	  echo -e "\e[1m If your software is based on the static objects edit the option at the line 50 of this PKGBUILD \e[0m "
	else
	  echo -e " Remove Static Objects: NO "
	fi
	echo -e "-----------------------------------------------------------------------------------"
	echo -e ""
	if  ${_remove_static_objects_ipp} ; then
	  echo -e ""
	  echo -e "\e[1m Remove Static Objects from IPP: YES \e[0m \e[1m\e[5m\e[31m ATTENTION !!!! \e[0m "
	  echo -e "\e[1m If your software is based on the static objects edit the option at the line 50 of this PKGBUILD \e[0m "
	else
	  echo -e " Remove Static Objects: NO "
	fi
	echo -e "-----------------------------------------------------------------------------------"
	echo -e ""
	echo -e ""


	cd ${xe_build_dir}/opt/intel
	ln -s ./${_composer_xe_dir} composerxe-${_year}
	ln -s ./composerxe-${_year} composerxe

	ln -s ./composerxe/bin/${_i_arch} bin
	ln -s ./composerxe/bin pkg_bin

	ln -s ./composerxe/ipp/ ipp
	ln -s ./composerxe/compiler/lib/${_i_arch} lib
	ln -s ./composerxe/debugger/lib/${_i_arch} debugger_lib
	ln -s ./composerxe/man/ man
	ln -s ./composerxe/mkl/ mkl
	ln -s ./composerxe/tbb/ tbb
	
	_current_dir=`pwd`
	if [ -d ${pkgdir}/opt ] ; then
	  cd ${pkgdir}
	  rm -rf opt
	  cd $_current_dir
	fi ;	

	cd  ${srcdir}/${_parallel_studio_xe_dir}/rpm
	rm -v -f *.${_not_arch2}.rpm
	cd $_current_dir
}

package_intel-compiler-base() {

	set_build_vars

	pkgdesc="Intel C/C++ compiler"
	pkgver=${_pkg_ver}
	install=intel-composer.install
	
	echo -e " # intel_compiler-base: Start Building" 

	mkdir -p ${xe_build_dir}/opt
	mkdir -p ${xe_build_dir}/etc/profile.d
	mkdir -p ${_man_dir}


	cp ${srcdir}/intel-compiler-base.conf ${xe_build_dir}/etc/ld.so.conf.d

	cd ${xe_build_dir}
	echo -e " # intel_compiler-base: Extracting RPMS" 
	
	extract_rpms 'intel-compilerpro-*.rpm'  $xe_build_dir
	extract_rpms 'intel-compilerproc-*.rpm'  $xe_build_dir
	
	echo -e " # intel_compiler-base: Editing variables" 
	cd ${xe_build_dir}/opt/intel/${_composer_xe_dir}/bin

	#rm uninstall.sh
	rm *.csh

	for f in *.sh ; do
	  sed -i 's/<PRODDIR>/\/opt\/intel/g' $f
	  sed -i 's/<INSTALLDIR>/\/opt\/intel\/composerxe/g' $f
	done 

	cd $_i_arch
	sed -i 's/<INSTALLDIR>/\/opt\/intel\/composerxe/g' loopprofileviewer.sh
	chmod a+x loopprofileviewer.sh
	rm loopprofileviewer.csh

	if $_remove_docs ; then
	  echo -e " # intel_compiler-base: Remove docs" 
	  rm -rf ${xe_build_dir}/opt/intel/${_composer_xe_dir}/documentation
	  rm -rf ${xe_build_dir}/opt/intel/${_composer_xe_dir}/Documentation
	  rm -rf ${xe_build_dir}/opt/intel/${_composer_xe_dir}/Samples
	fi

	echo -e " # intel_compiler-base: Coping man pages" 
        mv ${xe_build_dir}/opt/intel/${_composer_xe_dir}/man/en_US/man1/*.1 ${_man_dir}

	cd ${_man_dir}
	for f in *.1 ; do
	  gzip $f
	done

	cd ${xe_build_dir}

	echo -e " # intel_compiler-base: Move package"
	mv ${xe_build_dir}/opt ${pkgdir}
	mv ${xe_build_dir}/etc ${pkgdir}
	mv ${xe_build_dir}/usr ${pkgdir}
}


package_intel-fortran-compiler() {

	set_build_vars

	pkgdesc="Intel Fortran compiler"
	pkgver=${_pkg_ver}
	depends=('intel-compiler-base')
	install=intel-composer.install

	echo -e " # intel-fortran-compiler: Start Building" 

	mkdir -p ${xe_build_dir}/opt
	mkdir -p ${xe_build_dir}/etc/profile.d
	mkdir -p ${xe_build_dir}/etc/ld.so.conf.d
	mkdir -p ${_man_dir}

	if [ "$CARCH" = "i686" ]; then
	  sed 's/<arch>/ia32/' < ../intel-fortran.conf > ${xe_build_dir}/etc/ld.so.conf.d/intel-fortran.conf
	else
	  sed 's/<arch>/intel64/' < ../intel-fortran.conf > ${xe_build_dir}/etc/ld.so.conf.d/intel-fortran.conf
	fi

	cd ${xe_build_dir}
	
	echo -e " # intel-fortran-compiler: Extracting RPMS" 
	
	extract_rpms 'intel-compilerprof-*.rpm'  $xe_build_dir

	echo -e " # intel-fortran-compiler: Editing variables"
	cd ${xe_build_dir}/opt/intel/${_composer_xe_dir}/bin

	rm *.csh

	#rm ${xe_build_dir}/opt/intel/${_composer_xe_dir}/Documentation/en_US/gs_resources/intel_f_logo.gif
	#rm ${xe_build_dir}/opt/intel/${_composer_xe_dir}/compiler/lib/${_i_arch}/locale/ja_JP/diagspt.cat
	#rm ${xe_build_dir}/opt/intel/${_composer_xe_dir}/compiler/lib/${_i_arch}/locale/ja_JP/flexnet.cat
	#rm ${xe_build_dir}/opt/intel/${_composer_xe_dir}/compiler/lib/${_i_arch}/locale/ja_JP/helpxi.cat

	if $_remove_docs ; then
	  echo -e " # intel-fortran-compiler: Remove documentation"
	  rm -rf ${xe_build_dir}/opt/intel/${_composer_xe_dir}/documentation
	  rm -rf ${xe_build_dir}/opt/intel/${_composer_xe_dir}/Documentation
	  rm -rf ${xe_build_dir}/opt/intel/${_composer_xe_dir}/Samples
	fi

	echo -e " # intel-fortran-compiler: Coping man pages"
        mv ${xe_build_dir}/opt/intel/${_composer_xe_dir}/man/en_US/man1/*.1 ${_man_dir}

	cd ${_man_dir}
	for f in *.1 ; do
	  gzip $f
	done

	cd ${xe_build_dir}
	
	echo -e " # intel-fortran-compiler: Move package"
	mv ${xe_build_dir}/opt ${pkgdir}
	mv ${xe_build_dir}/etc ${pkgdir}
	mv ${xe_build_dir}/usr ${pkgdir}
}

package_intel-gdb() {

	set_build_vars

	pkgdesc="Intel C/C++ debugger"
	pkgver=${_pkg_ver}
	depends=('intel-compiler-base')
	replaces=('intel-idb')
	
	install=intel-composer.install
	echo -e " # intel-idb: Start Building"

	mkdir -p ${xe_build_dir}/opt
	mkdir -p ${xe_build_dir}/etc/ld.so.conf.d
	mkdir -p ${_man_dir}

	if [ "$CARCH" = "i686" ]; then
	  sed 's/<arch>/ia32/' < ../intel-idb.conf > ${xe_build_dir}/etc/ld.so.conf.d/intel-idb.conf
	else
	  sed 's/<arch>/intel64/' < ../intel-idb.conf > ${xe_build_dir}/etc/ld.so.conf.d/intel-idb.conf
	fi

	cd ${xe_build_dir}
	
	echo -e " # intel-gdb: Extracting RPS"
	extract_rpms 'intel-gdb*.rpm'  $xe_build_dir

	echo -e " # intel-gdb: Editing variables"
	cd ${xe_build_dir}/opt/intel/${_composer_xe_dir}/bin
	rm debuggervars.csh
	sed -i 's/<INSTALLDIR>/\/opt\/intel\/composerxe/g' debuggervars.sh

	#cd $_i_arch
	#rm debuggervars.csh
	#sed -i 's/<INSTALLDIR>/\/opt\/intel\/composerxe/g' debuggervars.sh
	#sed -i 's/<INSTALLDIR>/\/opt\/intel\/composerxe/g' gdb
	#sed -i 's/<INSTALLDIR>/\/opt\/intel\/composerxe/g' gdbc

	if $_remove_docs ; then
	  echo -e " # intel-gdb: Remove documentation"
	  rm -rf ${xe_build_dir}/opt/intel/${_composer_xe_dir}/Documentation
	fi

	echo -e " # intel-gdb: Coping man pages"
	mv ${xe_build_dir}/opt/intel/${_composer_xe_dir}/debugger/gdb/${_i_arch}/share/man/man1/*.1 ${_man_dir}

	cd ${_man_dir}
	for f in *.1 ; do
	  gzip $f
	done

	cd ${xe_build_dir}

	echo -e " # intel-gdb: Move package"

	mv ${xe_build_dir}/opt ${pkgdir}
	mv ${xe_build_dir}/etc ${pkgdir}
	mv ${xe_build_dir}/usr ${pkgdir}
}

package_intel-ipp() {

	set_build_vars

	pkgdesc="Intel Integrated Performance Primitives"
	pkgver=${_year}.${_ipp_ver}.${_v_b}
	#depends=('intel-compiler-base')
	install=intel-composer.install

	echo -e " # intel-ipp: Start Building"

	mkdir -p ${xe_build_dir}/opt

	mkdir -p ${xe_build_dir}/etc/ld.so.conf.d

	if [ "$CARCH" = "i686" ]; then
	  sed 's/<arch>/ia32/' < ${srcdir}/intel-ipp.conf > ${xe_build_dir}/etc/ld.so.conf.d/intel-ipp.conf
	else
	  sed 's/<arch>/intel64/' < ${srcdir}/intel-ipp.conf > ${xe_build_dir}/etc/ld.so.conf.d/intel-ipp.conf
	fi

	cd ${xe_build_dir}
	echo -e " # intel-ipp: Extracting RPMS"

	extract_rpms 'intel-ipp-*.rpm'  $xe_build_dir

	echo -e " # intel-ipp: Editing variables"
	cd ${xe_build_dir}/opt/intel/${_composer_xe_dir}/ipp/bin
	rm ippvars.csh
	sed -i 's/<INSTALLDIR>/\/opt\/intel\/composerxe/g' ippvars.sh

	cd $_i_arch
	rm ippvars_${_i_arch}.csh
	sed -i 's/<INSTALLDIR>/\/opt\/intel\/composerxe/g' ippvars_${_i_arch}.sh

        # remove the unneeded and problematic ipp_minigzip and ipp_gzip
	for _z_dir_name in 'ipp_zlib' 'ipp_gzip' 'ipp_bzip2'  ; do
	  rm -rf ${xe_build_dir}/opt/intel/${_composer_xe_dir}/ipp/interfaces/data-compression/${_z_dir_name}/bin/${_not_arch}
	done

	if ${_remove_docs} ; then
	  echo -e " # intel-ipp: Remove documentation"
	  rm -rf ${xe_build_dir}/opt/intel/${_composer_xe_dir}/Documentation
	fi

	if ${_remove_static_objects_ipp} ; then
	  echo -e " # intel-ipp: Remove static objects"
	  rm -f ${xe_build_dir}/opt/intel/${_composer_xe_dir}/ipp/lib/${_i_arch}/libipp*.a
	  rm -f ${xe_build_dir}/opt/intel/${_composer_xe_dir}/ipp/lib/${_i_arch}/nonpic/libipp*.a
	  rmdir ${xe_build_dir}/opt/intel/${_composer_xe_dir}/ipp/lib/${_i_arch}/nonpic/
	fi

	echo -e " # intel-ipp: Move package"
	mv ${xe_build_dir}/opt ${pkgdir}
	mv ${xe_build_dir}/etc ${pkgdir}
}

package_intel-mkl() {

	set_build_vars

	pkgdesc="Intel Math Kernel Library (Intel® MKL) "
	pkgver=${_year}.${_mkl_ver}.${_v_b}
	#depends=('intel-compiler-base')
	install=intel-mkl.install
	backup=('etc/intel-mkl-th.conf')

	echo -e " # intel-mkl: Start Building"

	mkdir -p ${xe_build_dir}/opt
	mkdir -p ${xe_build_dir}/etc/ld.so.conf.d
	
	mkdir -p ${xe_build_dir}/etc/profile.d

	cp ${srcdir}/intel-mkl.sh ${xe_build_dir}/etc/profile.d
	chmod a+x ${xe_build_dir}/etc/profile.d/intel-mkl.sh

	cp ${srcdir}/intel-mkl-th.conf ${xe_build_dir}/etc/

	if [ "$CARCH" = "i686" ]; then
	  sed 's/<arch>/ia32/' < ${srcdir}/intel-mkl.conf > ${xe_build_dir}/etc/ld.so.conf.d/intel-mkl.conf
	else
	  sed 's/<arch>/intel64/' < ${srcdir}/intel-mkl.conf > ${xe_build_dir}/etc/ld.so.conf.d/intel-mkl.conf
	fi

	cd ${xe_build_dir}
	
	echo -e " # intel-mkl: Extracting RPMS"
	extract_rpms 'intel-mkl-*.rpm'  $xe_build_dir

	echo -e " # intel-mkl: Editing variables"
	cd ${xe_build_dir}/opt/intel/${_composer_xe_dir}/mkl/bin
	rm mklvars.csh
	sed -i 's/<INSTALLDIR>/\/opt\/intel\/composerxe/g' mklvars.sh

	rm -rf ./${_not_arch}

	cd $_i_arch
	rm mklvars_${_i_arch}.csh
	sed -i 's/<INSTALLDIR>/\/opt\/intel\/composerxe/g' mklvars_${_i_arch}.sh

	if ${_remove_docs} ; then
	  echo -e " # intel-mkl: remove documentation"
	  rm -rf ${xe_build_dir}/opt/intel/${_composer_xe_dir}/Documentation
	  rm -rf ${xe_build_dir}/opt/intel/${_composer_xe_dir}/mkl/examples
	  rm -rf ${xe_build_dir}/opt/intel/${_composer_xe_dir}/mkl/benchmarks
	fi

	if ${_remove_static_objects_mkl} ; then
	  echo -e " # intel-mkl: remove static objects"
	  rm -f ${xe_build_dir}/opt/intel/${_composer_xe_dir}/mkl/lib/${_i_arch}/libmkl_*.a
	  rm -f ${xe_build_dir}/opt/intel/${_composer_xe_dir}/mkl/lib/mic/libmkl_*.a
	fi

	echo -e " # intel-mkl: Move package"
	mv ${xe_build_dir}/opt ${pkgdir}
	mv ${xe_build_dir}/etc ${pkgdir}
}

package_intel-openmp() {

	set_build_vars

	pkgdesc="Intel OpenMP Library"
	pkgver=${_year}.${_openmp_ver}.${_v_b}
	depends=('intel-compiler-base')
	install=intel-composer.install

	echo -e " # intel-openmp: Start Building"

	mkdir -p ${xe_build_dir}/opt

	mkdir -p ${xe_build_dir}/etc/ld.so.conf.d
	cp ${srcdir}/intel-openmp.conf ${xe_build_dir}/etc/ld.so.conf.d

	cd ${xe_build_dir}
	
	echo -e " # intel-openmp: Extracting RPMS"

	extract_rpms 'intel-openmp-*.rpm'  $xe_build_dir

	echo -e " # intel-openmp: Move package"
	mv ${xe_build_dir}/opt ${pkgdir}
	mv ${xe_build_dir}/etc ${pkgdir}
}

package_intel-sourcechecker() {

	set_build_vars

	pkgdesc="Intel Source Checker"
	pkgver=${_year}.${_sourcechecker_ver}.${_v_b}
	depends=('intel-compiler-base')

	echo -e " # intel-sourcechecker: Start building"

	mkdir -p ${xe_build_dir}/opt

	cd ${xe_build_dir}
	
	echo -e " # intel-sourcechecker: Extracting RPMS"

	extract_rpms 'intel-sourcechecker-*.rpm'  $xe_build_dir


	echo -e " # intel-sourcechecker: Move package"
	mv ${xe_build_dir}/opt ${pkgdir}
}

package_intel-tbb() {

	set_build_vars

	pkgdesc="Intel Threading Building Blocks (TBB)"
	pkgver=${_year}.${_tbb_ver}.${_v_b}
	#depends=('intel-compiler-base')
	install=intel-tbb.install

	echo -e " # intel-tbb: Start Building "

	mkdir -p ${xe_build_dir}/opt
	mkdir -p ${xe_build_dir}/etc/ld.so.conf.d

	if [ "$CARCH" = "i686" ]; then
	  sed 's/<arch>/ia32/' < ${srcdir}/intel-tbb.conf > ${xe_build_dir}/etc/ld.so.conf.d/intel-tbb.conf
	  sed -i 's/<INSTALLDIR>/\/opt\/intel\/composerxe/g' ${xe_build_dir}/etc/ld.so.conf.d/intel-tbb.conf
	else
	  sed 's/<arch>/intel64/' < ${srcdir}/intel-tbb.conf > ${xe_build_dir}/etc/ld.so.conf.d/intel-tbb.conf
	  sed -i 's/<INSTALLDIR>/\/opt\/intel\/composerxe/g' ${xe_build_dir}/etc/ld.so.conf.d/intel-tbb.conf
	fi

	cd ${xe_build_dir}
	
	echo -e " # intel-tbb: Extracting RPMS "
	extract_rpms 'intel-tbb-*.rpm'  $xe_build_dir


	echo -e " # intel-tbb: Editing variables "
	cd ${xe_build_dir}/opt/intel/${_composer_xe_dir}/tbb/bin
	rm tbbvars.csh

	sed -i 's/SUBSTITUTE_INSTALL_DIR_HERE/\/opt\/intel\/composerxe\/tbb/g' tbbvars.sh

	chmod a+x tbbvars.sh

	cd ${xe_build_dir}/opt/intel/${_composer_xe_dir}/tbb/bin
	#rm tbbvars.csh
	sed -i 's/SUBSTITUTE_INSTALL_DIR_HERE/\/opt\/intel\/composerxe\/tbb/g' tbbvars.sh
	chmod a+x tbbvars.sh

	echo -e " # intel-tbb: Remove unneeded libs and bin "
	rm -rf ${xe_build_dir}/opt/intel/${_composer_xe_dir}/tbb/bin/${_not_arch}	
	rm -rf ${xe_build_dir}/opt/intel/${_composer_xe_dir}/tbb/lib/${_not_arch}
	
	if $_remove_docs ; then
	  echo -e " # intel-tbb: remove documentation "
	  rm -rf ${xe_build_dir}/opt/intel/${_composer_xe_dir}/Documentation
	  rm -rf ${xe_build_dir}/opt/intel/${_composer_xe_dir}/tbb/examples
	fi

	echo -e " # intel-tbb: Move package "
	mv ${xe_build_dir}/opt ${pkgdir}
	mv ${xe_build_dir}/etc ${pkgdir}
}

package_intel-vtune-amplifier-xe() {
	pkgdesc="Performance profiler for serial and parallel performance analysis"
	pkgver=${_year}.${_vtune_ver}.${_v_b}
	depends=('pangox-compat')
	
	echo -e " # intel-vtune-amplifier-xe: Start building"
	mkdir -p ${xe_build_dir}/opt
	mkdir -p ${xe_build_dir}/etc/ld.so.conf.d
	mkdir -p ${_man_dir}
	
	echo -e " # intel-vtune-amplifier-xe: Editing variables "
	if [ "$CARCH" = "i686" ]; then
	  sed -i 's/<arch>/bin32/g' ${srcdir}/intel_vtune-amplifier-xe.sh
	else
	  sed -i 's/<arch>/bin64/g' ${srcdir}/intel_vtune-amplifier-xe.sh
	fi
	cp ${srcdir}/intel_vtune-amplifier-xe.sh ${xe_build_dir}/etc/ld.so.conf.d
	chmod a+x ${xe_build_dir}/etc/ld.so.conf.d/intel_vtune-amplifier-xe.sh
	
	cd ${xe_build_dir}
	echo -e " # intel-vtune-amplifier-xe: Extracting RPMS "
	extract_rpms 'intel-vtune-amplifier-xe-*.rpm'  $xe_build_dir
	
	echo -e " # intel-vtune-amplifier-xe: Coping man pages"
	mv ${xe_build_dir}/opt/intel/vtune_amplifier_xe_${_year}.${_vtune_ver}/man/man1/*.1 ${_man_dir}

	cd ${_man_dir}
	for f in *.1 ; do
	  gzip $f
	done
	
	if $_remove_docs ; then
	  echo -e " # intel-vtune-amplifier-xe: remove documentation "
	  rm -rf ${xe_build_dir}/opt/intel/vtune_amplifier_xe_${_year}.${_vtune_ver}/samples
	  rm -rf ${xe_build_dir}/opt/intel/vtune_amplifier_xe_${_year}.${_vtune_ver}/documentation
	fi	
	
	echo -e " # intel-vtune-amplifier-xe: Move package"
	mv ${xe_build_dir}/opt ${pkgdir}
	mv ${xe_build_dir}/etc ${pkgdir}
	mv ${xe_build_dir}/usr ${pkgdir}
}

package_intel-advisor-xe() {
	pkgdesc="Threading design and prototyping tool for software architects"
	pkgver=${_year}.${_advisor_ver}.${_v_b}
	
	echo -e " # intel-advisor-xe: Start building"
	mkdir -p ${xe_build_dir}/opt
	mkdir -p ${xe_build_dir}/etc/ld.so.conf.d
	mkdir -p ${_man_dir}	
	
	echo -e " # intel-advisor-xe: Editing variables "
	if [ "$CARCH" = "i686" ]; then
	  sed -i 's/<arch>/bin32/g' ${srcdir}/intel_advisor-xe.sh
	else
	  sed -i 's/<arch>/bin64/g' ${srcdir}/intel_advisor-xe.sh
	fi
	cp ${srcdir}/intel_advisor-xe.sh ${xe_build_dir}/etc/ld.so.conf.d
	chmod a+x ${xe_build_dir}/etc/ld.so.conf.d/intel_advisor-xe.sh	
	
	cd ${xe_build_dir}
	echo -e " # intel-advisor-xe: Extracting RPMS "
	extract_rpms 'intel-advisor-xe-*.rpm'  $xe_build_dir
	
	echo -e " # intel-advisor-xe: Coping man pages"
	mv ${xe_build_dir}/opt/intel/advisor_xe_${_year}.${_advisor_ver}/man/man1/*.1 ${_man_dir}

	cd ${_man_dir}
	for f in *.1 ; do
	  gzip $f
	done
	
	if $_remove_docs ; then
	  echo -e " # intel-vtune-amplifier-xe: remove documentation "
	  rm -rf ${xe_build_dir}/opt/intel/advisor_xe_${_year}.${_advisor_ver}/samples
	  rm -rf ${xe_build_dir}/opt/intel/advisor_xe_${_year}.${_advisor_ver}/documentation
	fi
	
	echo -e " # intel-advisor-xe: Move package"
	mv ${xe_build_dir}/opt ${pkgdir}
	mv ${xe_build_dir}/etc ${pkgdir}
	mv ${xe_build_dir}/usr ${pkgdir}
}

package_intel-inspector-xe() {
	pkgdesc="Memory and thread debugger"
	pkgver=${_year}.${_inspector_ver}.${_v_b}
	
	echo -e " # intel-inspector-xe: Start building"
	mkdir -p ${xe_build_dir}/opt
	mkdir -p ${xe_build_dir}/etc/ld.so.conf.d
	mkdir -p ${_man_dir}	
	
	echo -e " # intel-inspector-xe: Editing variables "
	if [ "$CARCH" = "i686" ]; then
	  sed -i 's/<arch>/bin32/g' ${srcdir}/intel_inspector-xe.sh
	else
	  sed -i 's/<arch>/bin64/g' ${srcdir}/intel_inspector-xe.sh
	fi
	cp ${srcdir}/intel_inspector-xe.sh ${xe_build_dir}/etc/ld.so.conf.d
	chmod a+x ${xe_build_dir}/etc/ld.so.conf.d/intel_inspector-xe.sh	
	
	cd ${xe_build_dir}
	echo -e " # intel-inspector-xe: Extracting RPMS "
	extract_rpms 'intel-inspector-xe-*.rpm'  $xe_build_dir
	
	echo -e " # intel-inspector-xe: Coping man pages"
	mv ${xe_build_dir}/opt/intel/inspector_xe_${_year}.${_inspector_ver}/man/man1/*.1 ${_man_dir}

	cd ${_man_dir}
	for f in *.1 ; do
	  gzip $f
	done
	
	if $_remove_docs ; then
	  echo -e " # intel-vtune-amplifier-xe: remove documentation "
	  rm -rf ${xe_build_dir}/opt/intel/inspector_xe_${_year}.${_inspector_ver}/samples
	  rm -rf ${xe_build_dir}/opt/intel/inspector_xe_${_year}.${_inspector_ver}/documentation
	fi
	
	echo -e " # intel-inspector-xe: Move package"
	mv ${xe_build_dir}/opt ${pkgdir}
	mv ${xe_build_dir}/etc ${pkgdir}
	mv ${xe_build_dir}/usr ${pkgdir}
}

pkgdesc="Intel C++ C and fortran compiler - Intel Parallel Studio XE  - intel compiler - icc icpc ifort ipp mkl "
depends=('bash' 'gcc')
