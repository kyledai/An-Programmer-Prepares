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
<BR>
每個層次之間都需要相互通信，既然需要通訊就必須要有一個通信協議。我們一般將其稱為接口。接口的下面那層是接口的提供者，由他定義接口；接口的上面那層是接口的使用者，他使用該接口來實現所需要的功能。<BR>

從整個層次結構上來看，開發工具與應用程式是屬於同一個層次的，因為它們都使用一個介面，那就是作業系統的應用程式開發介面。<BR>

應用程式介面的提供者是運行庫，Linux下Glibc的POSIX的API和Windows API Win32。運行庫使用作業系統提供的系統調用介面。系統調用介面在實現中往往以軟體插斷的方式提供。<BR>
