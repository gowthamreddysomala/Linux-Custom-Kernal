# Linux-Custom-Kernal<br>
<h4>Author : Gowtham Reddy </h4><br>

<h2>Instructions For Buidling Your Custom Kernal </h2><br>

Notice : This Kernal Was Build on Linux 6.7.2<br>

you can use wget in terminal with the link on Download button;<br>

example :  wget https://cdn.kernel.org/pub/linux/kernel/v6.x/linux-6.7.2.tar.xz<br><br>

extract the kernal using : tar xvf Kernal6.x.x,tar.xz<br>

this will take some time to extract the kernal <br>

get into that Directory using cd <br>

by default the .config file will not be there we need to make the one to customize the kernal.<br>

NOTE - the .config file contains the useful information to compile to what and what not to compile.<br>

use this command to make a config file :
make menuconfig -j8<br>
	 ^       ^ <br>
	 |       |________________________<br>
make GUI config selection           |<br>
to select whats needed              |<br>
							                      |<br>
                                    |<br>
			               			the total no of<br>
						              cores to run on<br>
						              specific process<br>
						             (this is flag)<br>



now you can see the lot of things that you need and not needed to the laptop or to the computer (you can customize the required stuff)<br>

<br><br><br><br>

--------------------------------------------------------------------------   start of customization  ---------------------------------------------------------------------------------------<br>

Tips :<br>
<br>
1) for faster boot times use <br>
		Kernal compression to ZSTD only.<br>
<br>
2)Disable POSTX Message Queues<br>
<br>
3)we can also disable Auditing Suppport<br>
<br>
4)Disable All Except ZSTD in initial RAM F]filesystem and Ram disk support<br>
<br>
<br>
5)configure Standard Kernal Features <br>
5)processor type and features <br>
 		->Disable AMD Stuff if you Have intel or do Vice Versa<br>
		->under Processor family select intel core 2 / newer Zeon<br>
<br>
		-> maximun no of cpu's (Enter no of threads you own in your pc)<br>
		-> Disable 5 - level page table Support<br>
<br>
<br>
6) Power management and ACPI Options:<br>
	->change performance governer as needed<br><br>
7)Virtualization is needed if you want to run virtual machines<br>
<br>
8)Enable the Block Layer<br>
	->Disable Block Layer Debugging(useful for kernal dev's - Bloat)<br>
<br>
9)in network read carefully and select <br>
<br>
10 ) Device Drivers <br>
	<br>
	->Disable PCCard <br>
	-> Enable all in NVME Support (cuz i use NVME)<br>
	-->in SCSI Enable Asynchronous SCSI Scanning<br>
	-->Disable RAID and LVM<br>
	-->Disable MAcintosh DeviceDrivers<br>
	-->Network Device Support<br>
		->disable usb network adapters<br>
		->Disable network console  logging support<br>
		->Enable Wireguard secure network tunnel (if u use VPN)<br>
	-->Input Device Support <br>
		->Disable Touch Screen,Miscellinous Device ,Tablets<br>
	->Enable Multi media Suppot<br>
	-->Graphics Support <br>
			-> Reduce maximum number of GPU's to 2<br>
			->Enable laptop Hybrid Grapics<br>
	<br>
	-->Sound Card Support <br>
		->Advanced Linux Sound Architecture<br>
			->PCI Sound Devices<br>
				->Enable all intel Stuff<br>
	-->Disable Accessablity Support<br>
	-->Enable X86 Platform Specific  Drivers<br>
		-->Enable intel Turbo Boost Max <br>
		-->if you find your laptop brand stuff enable them.<br>
	<br>
<br>
	-->Disable Microsoft Surface Platform Stuff<br>
	--> android <br>
		-->enable All<br>
<br>
11) File System <br>
		-->Disbale Network file system<br>


<br><br><br><br><br>



-----------------------------------------------------------------------------------------  End Of Customization ---------------------------------------------------------------------------<br><br>


<br>

save The Customized options and Exit .<br>


<br><br><br>
Time To Compile The Kernal That We Built !!<br>
<br>
___________________________________________
 <br>
<br>

use this Commands to compile : make -j8  && sudo make modules_install -j8<br>


<br>
it Take's  Some Time To Compile ..<br>
<br>
<br>

backup the old kernal file and Repalce it with new one<br>

you can find your current Kernal in /boot/vmlinux-linux <br>
<br>
vmlinuz-linux is the kernal <br>
<br>

copy the kernal to /boot<br>

<br>
ex : sudo cp arch/x86/boot/bzimage  /boot/vmlinuz-linuxgowtham<br>
<br>
Reconfigre the boot loader<br>
<br>
sudo grub-mkconfig-o /boot/grub/grub.cfg<br>

<br>
Its Done !!
<br>
<h3>Thanks To : </h3><br><br>
No One !<br><br>
 This is my effort !<br><br>
 But this is Completly Legal .<br><br>
 <h4>XMR Wallet Address: 47WDZLhN3VHbvfYqbuMLo4XNt5C4Ehtfbc3krR2RnCx3Wb9FaCRxh5h4oTCa3KW2UgRU9koxudbTr7wQxFe45maRAfogQSq </h4><br><br>
ThankYou..
 




