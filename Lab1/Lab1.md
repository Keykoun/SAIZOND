<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" xml:lang="en"><head>

<meta charset="utf-8">
<meta name="generator" content="quarto-1.2.269">

<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">




</head>

<body class="fullcontent">

<div id="quarto-content" class="page-columns page-rows-contents page-layout-article">

<main class="content" id="quarto-document-content">

<header id="title-block-header" class="quarto-title-block default">
<div class="quarto-title">
<h1 class="title">Lab1</h1>
</div>



<div class="quarto-title-meta">

    
  
    
  </div>
  

</header>

<section id="системы-аутентификации-и-защиты-от-несанкционированного-доступа" class="level1">
<h1>Системы аутентификации и защиты от несанкционированного доступа</h1>
<p>Лабораторная работа №1</p>
<section id="цель" class="level2">
<h2 class="anchored" data-anchor-id="цель">Цель</h2>
<p>Вывести информацию о системе</p>
</section>
<section id="исходные-данные" class="level2">
<h2 class="anchored" data-anchor-id="исходные-данные">Исходные данные</h2>
<ol type="1">
<li>ОС Windows 10</li>
<li>RStudio Desktop</li>
<li>Интерпретатор языка R 4.2.2</li>
</ol>
</section>
<section id="план" class="level2">
<h2 class="anchored" data-anchor-id="план">План</h2>
<ol type="1">
<li>Выполнить команду system2(“systeminfo”, stdout = TRUE)</li>
<li>Выполнить команду system(“wmic cpu get name”)</li>
<li>Выполнить команду system(“powershell.exe Get-EventLog -LogName System -Newest 30”)</li>
</ol>
</section>
<section id="шаги" class="level2">
<h2 class="anchored" data-anchor-id="шаги">Шаги</h2>
<ol type="1">
<li>Сначала выполним команду system2(“systeminfo”, stdout = TRUE) для вывода информации о системе</li>
</ol>
<div class="cell">
<div class="sourceCode cell-code" id="cb1"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb1-1"><a href="#cb1-1" aria-hidden="true" tabindex="-1"></a><span class="fu">system2</span>(<span class="st">"systeminfo"</span>, <span class="at">stdout =</span> <span class="cn">TRUE</span>)</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stdout">
<pre><code> [1] ""                                                                                                               
 [2] "Host Name:                 DESKTOP-FPUNF0R"                                                                     
 [3] "OS Name:                   Microsoft Windows 10 Pro"                                                            
 [4] "OS Version:                10.0.19045 N/A Build 19045"                                                          
 [5] "OS Manufacturer:           Microsoft Corporation"                                                               
 [6] "OS Configuration:          Standalone Workstation"                                                              
 [7] "OS Build Type:             Multiprocessor Free"                                                                 
 [8] "Registered Owner:          RR"                                                                                  
 [9] "Registered Organization:   N/A"                                                                                 
[10] "Product ID:                00330-80000-00000-AA577"                                                             
[11] "Original Install Date:     06.03.2021, 22:54:18"                                                                
[12] "System Boot Time:          20.05.2023, 11:37:24"                                                                
[13] "System Manufacturer:       Gigabyte Technology Co., Ltd."                                                       
[14] "System Model:              Z270-HD3"                                                                            
[15] "System Type:               x64-based PC"                                                                        
[16] "Processor(s):              1 Processor(s) Installed."                                                           
[17] "                           [01]: Intel64 Family 6 Model 158 Stepping 9 GenuineIntel ~4201 Mhz"                  
[18] "BIOS Version:              American Megatrends Inc. F4, 10.02.2017"                                             
[19] "Windows Directory:         C:\\WINDOWS"                                                                         
[20] "System Directory:          C:\\WINDOWS\\system32"                                                               
[21] "Boot Device:               \\Device\\HarddiskVolume2"                                                           
[22] "System Locale:             en-us;English (United States)"                                                       
[23] "Input Locale:              ru;Russian"                                                                          
[24] "Time Zone:                 (UTC+03:00) Moscow, St. Petersburg"                                                  
[25] "Total Physical Memory:     16\xff343 MB"                                                                        
[26] "Available Physical Memory: 10\xff052 MB"                                                                        
[27] "Virtual Memory: Max Size:  24\xff023 MB"                                                                        
[28] "Virtual Memory: Available: 15\xff029 MB"                                                                        
[29] "Virtual Memory: In Use:    8\xff994 MB"                                                                         
[30] "Page File Location(s):     C:\\pagefile.sys"                                                                    
[31] "Domain:                    WORKGROUP"                                                                           
[32] "Logon Server:              \\\\DESKTOP-FPUNF0R"                                                                 
[33] "Hotfix(s):                 24 Hotfix(s) Installed."                                                             
[34] "                           [01]: KB5022502"                                                                     
[35] "                           [02]: KB4562830"                                                                     
[36] "                           [03]: KB4577586"                                                                     
[37] "                           [04]: KB4580325"                                                                     
[38] "                           [05]: KB4589212"                                                                     
[39] "                           [06]: KB4598481"                                                                     
[40] "                           [07]: KB5003791"                                                                     
[41] "                           [08]: KB5012170"                                                                     
[42] "                           [09]: KB5015684"                                                                     
[43] "                           [10]: KB5026361"                                                                     
[44] "                           [11]: KB5006753"                                                                     
[45] "                           [12]: KB5007273"                                                                     
[46] "                           [13]: KB5011352"                                                                     
[47] "                           [14]: KB5011651"                                                                     
[48] "                           [15]: KB5014032"                                                                     
[49] "                           [16]: KB5014035"                                                                     
[50] "                           [17]: KB5014671"                                                                     
[51] "                           [18]: KB5015895"                                                                     
[52] "                           [19]: KB5016705"                                                                     
[53] "                           [20]: KB5020372"                                                                     
[54] "                           [21]: KB5022924"                                                                     
[55] "                           [22]: KB5023794"                                                                     
[56] "                           [23]: KB5025315"                                                                     
[57] "                           [24]: KB5005699"                                                                     
[58] "Network Card(s):           5 NIC(s) Installed."                                                                 
[59] "                           [01]: Intel(R) Ethernet Connection (2) I219-V"                                       
[60] "                                 Connection Name: Ethernet"                                                     
[61] "                                 Status:          Media disconnected"                                           
[62] "                           [02]: ASUS USB-AC51 USB Wireless adapter"                                            
[63] "                                 Connection Name: Wi-Fi"                                                        
[64] "                                 DHCP Enabled:    Yes"                                                          
[65] "                                 DHCP Server:     192.168.1.254"                                                
[66] "                                 IP address(es)"                                                                
[67] "                                 [01]: 192.168.1.77"                                                            
[68] "                                 [02]: fe80::9a48:5950:1ef2:71bd"                                               
[69] "                                 [03]: fd98:723f:c268:1:d8d4:e357:310d:b8b4"                                    
[70] "                                 [04]: 2a00:1370:819a:5a4:d8d4:e357:310d:b8b4"                                  
[71] "                                 [05]: fd98:723f:c268:1:3722:7b74:bd94:b71f"                                    
[72] "                                 [06]: 2a00:1370:819a:5a4:630d:f78b:7eae:9b63"                                  
[73] "                                 [07]: 2a00:1370:819a:5a4:e99:5cea:51ce:cd90"                                   
[74] "                           [03]: VMware Virtual Ethernet Adapter for VMnet1"                                    
[75] "                                 Connection Name: VMware Network Adapter VMnet1"                                
[76] "                                 DHCP Enabled:    Yes"                                                          
[77] "                                 DHCP Server:     192.168.40.254"                                               
[78] "                                 IP address(es)"                                                                
[79] "                                 [01]: 192.168.40.1"                                                            
[80] "                                 [02]: fe80::9cab:e5fc:1a5a:ed0e"                                               
[81] "                           [04]: VMware Virtual Ethernet Adapter for VMnet8"                                    
[82] "                                 Connection Name: VMware Network Adapter VMnet8"                                
[83] "                                 DHCP Enabled:    Yes"                                                          
[84] "                                 DHCP Server:     192.168.25.254"                                               
[85] "                                 IP address(es)"                                                                
[86] "                                 [01]: 192.168.25.1"                                                            
[87] "                                 [02]: fe80::f9b9:9506:bbae:6911"                                               
[88] "                           [05]: VirtualBox Host-Only Ethernet Adapter"                                         
[89] "                                 Connection Name: Ethernet 2"                                                   
[90] "                                 DHCP Enabled:    No"                                                           
[91] "                                 IP address(es)"                                                                
[92] "                                 [01]: 192.168.56.1"                                                            
[93] "                                 [02]: fe80::b39:40d4:7639:52e5"                                                
[94] "Hyper-V Requirements:      A hypervisor has been detected. Features required for Hyper-V will not be displayed."                       </code></pre>
</div>
</div>
<p>2. Далее команда system(“wmic cpu get name”) для вывода информации о процессоре</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb3"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb3-1"><a href="#cb3-1" aria-hidden="true" tabindex="-1"></a><span class="fu">system2</span>(<span class="st">"cmd"</span>, <span class="at">args =</span> <span class="fu">c</span>(<span class="st">"/c"</span>, <span class="st">"wmic cpu get name"</span>), <span class="at">stdout =</span> <span class="cn">TRUE</span>)</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stdout">
<pre><code>[1] "Name                                      \r"
[2] "Intel(R) Core(TM) i7-7700K CPU @ 4.20GHz  \r"
[3] "\r"                                 </code></pre>
</div>
</div>
<p>3. Также выполним команду system(“powershell.exe Get-EventLog -LogName System -Newest 30”) для вывода логов</p>
<div class="cell">
<div class="sourceCode cell-code" id="cb5"><pre class="sourceCode r code-with-copy"><code class="sourceCode r"><span id="cb5-1"><a href="#cb5-1" aria-hidden="true" tabindex="-1"></a><span class="fu">system2</span>(<span class="st">"powershell.exe"</span>, <span class="at">args =</span> <span class="fu">c</span>(<span class="st">"Get-EventLog"</span>, <span class="st">"-LogName"</span>, <span class="st">"System"</span>, <span class="st">"-Newest"</span>, <span class="st">"30"</span>), <span class="at">stdout =</span> <span class="cn">TRUE</span>)</span></code><button title="Copy to Clipboard" class="code-copy-button"><i class="bi"></i></button></pre></div>
<div class="cell-output cell-output-stdout">
<pre><code> [1] ""                                                                                                                       
 [2] "   Index Time          EntryType   Source                 InstanceID Message                                           "
 [3] "   ----- ----          ---------   ------                 ---------- -------                                           "
 [4] "   37627 ??? 20 12:00  Information EventLog               2147489661 The system uptime is 1355 seconds.                "
 [5] "   37626 ??? 20 11:48  Information Microsoft-Windows...           19 Installation Successful: Windows successfully i..."
 [6] "   37625 ??? 20 11:48  Information Service Control M...   1073748869 A service was installed in the system....         "
 [7] "   37624 ??? 20 11:48  Information Microsoft-Windows...           43 Installation Started: Windows has started insta..."
 [8] "   37623 ??? 20 11:48  Information Microsoft-Windows...           44 Windows Update started downloading an update.     "
 [9] "   37622 ??? 20 11:47  Information Service Control M...   1073748864 The start type of the Background Intelligent Tr..."
[10] "   37621 ??? 20 11:45  Information Service Control M...   1073748864 The start type of the Background Intelligent Tr..."
[11] "   37620 ??? 20 11:40  Information Service Control M...   1073748869 A service was installed in the system....         "
[12] "   37619 ??? 20 11:39  Warning     DCOM                        10016 The description for Event ID '10016' in Source ..."
[13] "   37618 ??? 20 11:39  Warning     DCOM                        10016 The description for Event ID '10016' in Source ..."
[14] "   37617 ??? 20 11:39  Warning     DCOM                        10016 The description for Event ID '10016' in Source ..."
[15] "   37616 ??? 20 11:39  Information Microsoft-Windows...            5 Secure Trustlet NULL Id 0 and Pid 0 started wit..."
[16] "   37615 ??? 20 11:39  Error       VBoxNetLwf             3221487628 The driver detected an internal driver error on..."
[17] "   37614 ??? 20 11:37  Warning     DCOM                        10016 The description for Event ID '10016' in Source ..."
[18] "   37613 ??? 20 11:37  Warning     Microsoft-Windows...         1014 Name resolution for the name www.bing.com timed..."
[19] "   37612 ??? 20 11:37  Information Microsoft-Windows...            6 File System Filter 'gameflt' (10.0, 2035-08-12T..."
[20] "   37611 ??? 20 11:37  Information Service Control M...   3221232498 The following boot-start or system-start driver..."
[21] "   37610 ??? 20 11:37  Warning     e1dexpress             2684616731 Intel(R) Ethernet Connection (2) I219-V...        "
[22] "   37609 ??? 20 11:37  Error       VBoxNetLwf             3221487628 The driver detected an internal driver error on..."
[23] "   37608 ??? 20 11:37  Information Microsoft-Windows...         4000 WLAN AutoConfig service has successfully starte..."
[24] "   37607 ??? 20 11:37  Information vmx86                  1074266146 The description for Event ID '1074266146' in So..."
[25] "   37606 ??? 20 11:37  Error       VBoxNetLwf             3221487628 The driver detected an internal driver error on..."
[26] "   37605 ??? 20 11:37  Information VMnetuserif            1074135041 () Starting up the User Interface Driver for VM..."
[27] "   37604 ??? 20 11:37  Information Microsoft-Windows...          277 vmswitch.sys build 19041.amd64.vb_release_svc_p..."
[28] "   37603 ??? 20 11:37  Information VMnetBridge            1074200586 () Starting up the Bridge Driver for VMware Vir..."
[29] "   37602 ??? 20 11:37  Information Microsoft-Windows...         7001 User Logon Notification for Customer Experience..."
[30] "   37601 ??? 20 11:37  Information Microsoft-Windows...        51046 DHCPv6 client service is started                  "
[31] "   37600 ??? 20 11:37  Information Microsoft-Windows...        50103 DHCPv4 client registered for shutdown notification"
[32] "   37599 ??? 20 11:37  Information Microsoft-Windows...        50036 DHCPv4 client service is started                  "
[33] "   37598 ??? 20 11:37  Information Microsoft-Windows...            6 File System Filter 'bindflt' (10.0, 2005-08-08T..."
[34] ""                                                                                                                       
[35] ""                                                                                                                       
>                                                                                                                          </code></pre>
</div>
</div>
</section>
<section id="оценка-результата" class="level2">
<h2 class="anchored" data-anchor-id="оценка-результата">Оценка результата</h2>
<p>В результате лабораторной работы мы получили основную информацию об ОС, процессоре и логи системы.</p>
</section>
<section id="вывод" class="level2">
<h2 class="anchored" data-anchor-id="вывод">Вывод</h2>
<p>Таким образом, мы научились работать с базовыми командами командой строки и получать информацию об операционной системе.</p>
</section>
</section>

</main>
<!-- /main column -->
</div> <!-- /content -->
</body></html>
