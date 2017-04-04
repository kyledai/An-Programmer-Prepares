第一章-溫故而知新(讀後心得)

程式設計在現在稱不上顯學，是一個離現實較遠，不那麼爲世人矚目的學問。<BR>
但在工業4.0的現代結合自動化生產、機器人、物聯網的勢必是可改變人類生活型態的技術。<BR>

第一章-溫故而知新：介紹基本的硬體知識，包括硬體、作業系統、程序等。

1.1從Hello World說起<BR>
<img src="https://github.com/kyledai/An-Programmer-Prepares/blob/master/Chapter1_Image/questionabouthelloworld.jpg" width="640"/><BR>
一個Hello World會有這麼多問題，我會逐漸介紹，如何載入程式庫等等的內容...<BR>

1.2萬變不離其宗<BR>
早期的電腦架構(如下圖)<BR>
<img src="https://github.com/kyledai/An-Programmer-Prepares/blob/master/Chapter1_Image/1_1computerarchitecture.jpg" width="640"/><BR>
早期CPU頻率不高記憶體頻率也不高，可以使用一樣的匯流排。<BR>
採用PCI/ISA及南北橋設計的硬體架構(如下圖)<BR>
<img src="https://github.com/kyledai/An-Programmer-Prepares/blob/master/Chapter1_Image/1_2computerarchitecture.jpg" width="640"/><BR>

1.3站的高，望得遠<BR>
"電腦科學領域的任何問題都可以透過另一個中間層而得以解決"<BR>
電腦軟體架構(如下圖)<BR>
<img src="https://github.com/kyledai/An-Programmer-Prepares/blob/master/Chapter1_Image/1_3computerswarchitecture.jpg" width="640"/><BR>
每個層次之間都需要相互通信，既然需要通訊就必須要有一個通信協議。我們一般將其稱為接口。接口的下面那層是接口的提供者，由他定義接口；接口的上面那層是接口的使用者，他使用該接口來實現所需要的功能。<BR>

從整個層次結構上來看，開發工具與應用程式是屬於同一個層次的，因為它們都使用一個介面，那就是作業系統的應用程式開發介面。<BR>

應用程式介面的提供者是運行庫，Linux下Glibc的POSIX的API和Windows API Win32。運行庫使用作業系統提供的系統調用介面。系統調用介面在實現中往往以軟體插斷的方式提供。<BR>

1.4作業系統的功能<BR>
主要是提供一個抽象的介面，另一個功能是管理資源。<BR>
電腦資源主要分成，CPU、記憶體和I/O設備。<BR>

1.4.1不要讓CPU打盹<BR>
每個行程(Process)會根據優先順序的高低得到CPU的資源。但是如果執行時間超出一定得分配，作業系統會強制剝奪CPU資源並分配給目前最需要的行程。這種分配方式即所謂的先佔式(Preemptive)。目前所有現代的系統都採用此種方式，比如UNIX、Linux、Windows NT、Mac OS X。<BR>

1.4.2設備驅動程式<BR>
作業系統的開發者為硬體生產商提供一系列介面跟框架，凡是按照這個介面框架開發的驅動程式，都可以在作業系統上使用。<BR>

1.5記憶體不夠怎麼辦<BR>
作業系統的多功能使得CPU能夠在多個行程之間妥善共用，從行程的角度看好像是他獨佔了CPU，而不用考慮與其他行程分享CPU的事。作業系統的I/O抽象模型也將I/O設備的共用和抽象實做作的很好，那剩下的就是記憶體分配的問題。<BR>

早期電腦程式是直接執行在實體記憶體上的，但現在為了提升效率的多工一次需要執行多個程式，如何將電腦有限的記憶體分配給多個程式使用。<BR>
需考慮以下三種記憶體分配問題<BR>
。位址空間的不隔離：怕程式有可能改寫到其他地址的資料。<BR>
。記憶體使用效率低：若記憶體空間不族可能會有程式大量換入換出的需求。<BR>
。程式執行的地址不確定：每次載入執行時，這空閒區域的位置是不確定的，會很麻煩，因為程式編寫時有些轉跳指令、存取指令需要固定的地址。<BR>
