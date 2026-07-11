> [!summary] Note for writer, ignore this
>  - **Problems**: What problems am I  getting? (Scratching my own itch)
>  - **Validate Problems:** Are these problems occur in other people's lives? (Is there a demand? Is the pain any real and is the product really wanted?)
> - Is there already a cure? 
> 	- If yes, how and why it works? 
> 	- What can be improved from such products? 
> - Apa yang bisa kita tawarkan? Apakah mampu bagi kita untuk bersaing? 
> - Strategi untuk mendapat 'pengguna' pertama -> Open source-ing core features
> - Strategi untuk monetisasi -> Additional benefits for paid users
> - How these strategy works? We'll find out after 1 month of launching
> Report

# Study Case: Multiformat Saver for Archiving the Web

tags: #reflections #building #business
# Problems
Menyimpan konten internet  sebenarnya cukup mudah. Fitur bookmarking konvensional yang berada pada browser menyelesaikan permasalahan ini jauh sebelum aplikasi *notetaking* seperti Notion, Obsidian, dan Evernote dengan plugin web clipper mereka masing-masing.

 Namun sebagai *[product builder](https://vaujan.github.io/)*, aku kesulitan menemukan solusi *bookmarking* atau *content saver* yang seusai dengan kebutuhanku: yaitu menyimpan gambar, url (bookmarking) dan teks yang teroganisir. Sebagai contoh, ketika kita menemukan sebagai video di YouTube, mudah untuk menyimpannya: dengan web clipper contohnya. Menyimpan artikel, blog post, atau tweet juga bisa selesai dengan *workflow* yang sama.  

![[Pasted image 20260707114148.png]]

Akan tetapi, bagaimana jika yang ingin kita simpan adalah *screenshot* komponen UI untuk dijadikan inspirasi (semisal screenshot search bar pada YouTube) atau *reference board*? Bagaimana jika screenshot tersebut ingin kita simpan dalam satu folder yang sama dengan URL, dan teks file lain? 

Aku menemukan keperluan mengorganisir URL (YouTube video, tweet, etc.), gambar, dan teks dalam satu folder karena terkadang setiap item bisa memiliki konteks organisasi yang sama. Sebagai contoh: 
- Folder 'Productivity SaaS Project', berisi: (a) tweet tentang *user demand* atau *pain points* yang ada dalam *existing solution*, (b) refleksi atau development log berupa teks file project tersebut, dan juga (c) screenshot bagaimana referensi UI yang ingin dicapai
- Folder 'Kettlebell Training', berisi: (a) video YouTube program kettlebell, (b) log dan catatan latihan, serta (c) gambar mengenai form gerakan atau dokumentasi latihan

![[Pasted image 20260707140514.png]]

Secara sekilas, tidak ada solusi *out-of-the-box* yang muncul sebagai *top-of-mind*. Mungkin Notion. Notion memillki kapabilitas menyelesaikan permasalahan ini, namun dengan konfigurasi dan kustomisasi yang tentu memerlukan pengetahuan dasar tentang aplikasi tersebut. Lagi pula, Notion lebih cocok digunakan pada kasus pengembangan *knowledge base* atau *second brain* yang menginginkan fleksibiltas maksimal. Fleksibilitas yang menjadi nilai plus terbaik Notion juga sekaligus menjadi titik terlemahnya: yaitu tidak ada *out-of-the-box experience* dan sangat mudah untuk tergelincir pada *neraka konfigurasi*.

Menggunakan Notion dalam untuk meorganisir organisas project sederhana seperti membunuh kecoak menggunakan *bazooka*. (*It's overkill*)

> [!example] Catatan menarik mengenai use case Notion
 >1. ["This is configuration hell. Sharpening your axe until there is no axe left to sharpen and the tree you were going to fell has already rotted away".](https://kami.bearblog.dev/configuration-hell/)
>  2. ["Notion is not a productivity tool. Notion is a tool for feeling productive while accomplishing nothing."](https://ilikekillnerds.com/2026/01/20/notion-is-where-productivity-goes-to-die/) 

Setelah Notion kita coret, Evernote dan Obsidian adalah kandidat yang sangat menarik (p.s blog post ditulis di Obsidian). Tapi kedua produk tersebut memiliki fungsi utama sebagai pencatat (*notetaker*). *That's it*. Markdown file, text file — yang disimpan ke dalam sebuah folder. 

![[Pasted image 20260707140429.png]]

URL yang tersimpan ketika menggunakan web clipper, browser extension resmi resmi dari Obsidian, akan berbentuk file markdown. Selain dari ketidaknyamanan *minor* dari sisi UX, Obsidian juga tidak memiliki fitur overview dari semua item yang ada dalam sebuah folder. *Everything is a note* dan mengubah konvensi tersebut bukan pilihan (mungkin ada opsi community plugin, *but it's very likely to break and is painful to setup*)

--- 
Setelah menanyakan kebutuhan produk yang kujelaskan ke LLM (dalam hal ini ChatGPT, here's the public [link](https://chatgpt.com/share/6a51b41b-0eb4-83ec-8a52-54e6a45a05d5)), beberapa referensi menarik yang diberikan antara lain: 
1. **Bookmark managers**: Instapaper, Raindrop.io, Pocket
2. **Visual Asset Managers**: Eagle, PureRef, Adobe Bridge
3. **Personal Knowledge Management (PKM)**: Notion, LogSeq, Obsidian
4. **Creative Research Platforms**: Are.na, Cosmos, Milanote, Fabric

Bookmark managers dan visual asset managers tentu aku coret, sangat terbatas dari segi fitur: hanya terfokus pada satu format item — URL saja atau asset visual saja. Dan *personal knowledge management* seperti Notion dan Obsidian terlalu overkill dan perlu konfigurasi khusus — dan itu pun masih memberikan pengalaman menggunakan yang natural dan intuitif. 

Solusi pada *creative research platforms* memiliki use case yang sangat mendekati permasalahan yang coba kita selesaikan.
- Misalnya **[Cosmos](https://www.cosmos.so/)**, secara sekilas memilki *use case* yang sangat mirip dengan Pinterest, yaitu sebagai plaform pencari referensi dan insipirasi visual. Beberapa fitur yang menarik perhatianku: "Hide AI Content" dan "Search by Color". UI-nya juga elegan, minimalis dan terlihat sangat intuitif. Meski tertarik dengan konsep produk tersebut, aku tidak mencobanya secara langsung karena ini jelas bukan yang aku cari. 
- **[Milanote](https://milanote.com/)** menggunakan konsep *infinite canvas* sebagai inti dari produk mereka. Sangat berguna untuk bekerja dengan berbagai macam *resource* dan menyambungkannya secara visual. Lagi-lagi: menarik, tapi bukan fitur yang aku butuhkan.  
- [**Fabric**](https://fabric.so/) memiliki fitur yang persis aku butuhkan: penyimpanan multfiformat yang teroganisir dalam satu folder. ![[Pasted image 20260711160957.png]]
- Sama halnya dengan [**Are.na**](https://www.are.na/)  , bisa aku sederhanakan bahwa Are.na sama seperti Pinterest, namun bisa digunakan untuk menyimpan item dengan format lain, selain gambar. ![[Pasted image 20260711174229.png]]

**Are.na** dan **Fabric** adalah produk cukup baik dalam segi jika hanya dinilai pada kemampuannya untuk mengorganisir file multiformat. Namun aspek penting lainnya juga menentukan pengguna untuk meggunakan dan tetap bertahan dengan sebuah produk, seperti: *pricing*, *privacy concern*, *user interface/experience*, AI integration dan lainnya. 

---
# Kenapa study case ini dibuat
*I am cherrypicking my research? Maybe.*  Namun, tujuan utamaku saat ini tidak sedang berfokus untuk menyelesaikan permasalahan yang ada di market. Tidak. Aku ingin menyelesaikan permasalahan ini untuk diriku sendiri dan acuan dari research ini adalah: permasalahan yang aku alami tidak eksklusif, dan terverfiikasi bahwa dialami juga oleh orang lain. 

Tujuan utama aku membuat study case ini adalah untuk mempelajari ulang secara mendalam bagaimana proses pembuatan sebuah produk, mulai dari ide hingga deploy. Namun di satu sisi juga untuk mendokumentasikan perjalananku membuat suatu solusi atas masalah aku alami secara pribadi (*scratching my own itch*!).

--- 

Vibe coding membuat entry fee dalam membuat produk sangat rendah, sehingga kemampuan untuk membuat produk tidak lagi dianggap spesial atau faktor pembeda seseorang.

It's very easy to start on the action and we can all see the good side of it. But what about the bad side of it?