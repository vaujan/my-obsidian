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
**tags**: #reflections #building #business 
**links**: [Excalidraw](https://excalidraw.com/#json=LbQvTMWjflk4XXTotiISI,0M8JbXl_7Qjq7PSxRBaTLw)

## Problems 
Menyimpan konten internet  sebenarnya cukup mudah. Fitur bookmarking konvensional yang berada pada browser menyelesaikan permasalahan ini jauh sebelum aplikasi *notetaking* seperti Notion, Obsidian, dan Evernote dengan plugin web clipper mereka masing-masing.

 Namun sebagai *[product builder](https://vaujan.github.io/)*, aku kesulitan menemukan solusi *bookmarking* atau *content saver* yang seusai dengan kebutuhanku: yaitu menyimpan gambar, URL (bookmarking) dan teks yang terorganisir. Sebagai contoh, ketika kita menemukan sebagai video di YouTube, mudah untuk menyimpannya — dengan web clipper contohnya. Hal ini menyelesaikan permasalahan dalam menyimpan artikel, blog post, atau tweet.  

![[Pasted image 20260707114148.png]]

Tapi bagaimana jika yang ingin kita simpan adalah *screenshot* komponen UI untuk dijadikan inspirasi (semisal screenshot search bar pada YouTube) untuk kemudian secara keseluruhan dengan gambar sebagai *reference board*? Bagaimana jika *screenshot* atau gambar tersebut ingin kita simpan dalam satu folder yang sama dengan URL, dan teks file lain? 

Aku menemukan keperluan mengorganisir URL (YouTube video, tweet, etc.), gambar, dan teks dalam satu folder karena terkadang setiap item bisa memiliki konteks pengorganisasian yang sama. Sebagai contoh: 
- Folder 'Productivity SaaS Project', berisi: (a) tweet tentang *user demand* atau *pain points* yang ada dalam *niche productivity*, (b) refleksi atau development log berupa teks file project tersebut, dan juga (c) screenshot bagaimana referensi UI yang ingin dicapai
- Folder 'Kettlebell Training', berisi: (a) video YouTube program kettlebell, (b) log dan catatan latihan, serta (c) gambar mengenai form gerakan atau dokumentasi latihan

![[Pasted image 20260712190613.png]]

Ketika pikirkan secara sekilas, tidak ada solusi *out-of-the-box* yang muncul sebagai *top-of-mind*. Mungkin Notion. Notion memiliki kapasitas untuk menyelesaikan permasalahan ini, namun dengan konfigurasi dan kustomisasi yang tentu memerlukan pengetahuan dasar tentang aplikasi tersebut. Lagi pula, Notion lebih cocok digunakan pada kasus pengembangan *knowledge base* atau *second brain* yang menginginkan fleksibilitas maksimal. Fleksibilitas yang menjadi nilai plus terbaik Notion juga sekaligus menjadi titik terlemahnya: yaitu tidak ada *out-of-the-box experience* dan sangat mudah untuk tergelincir pada *neraka konfigurasi*.

> Aku mencoba kembali ke Notion setelah beberapa tahun meninggalkannya untuk Obsidian. *It looks like a completely different app*. *Notion does so much more than just a notetaking app now and that's a problem (at least for me).* 

Menggunakan Notion dalam untuk mengorganisir project sederhana rasanya seperti membunuh kecoak menggunakan *bazooka*. (*It's overkill*)

> [!example] Catatan menarik mengenai use case Notion
 >1. ["This is configuration hell. Sharpening your axe until there is no axe left to sharpen and the tree you were going to fell has already rotted away".](https://kami.bearblog.dev/configuration-hell/)
>  2. ["Notion is not a productivity tool. Notion is a tool for feeling productive while accomplishing nothing."](https://ilikekillnerds.com/2026/01/20/notion-is-where-productivity-goes-to-die/) 

Setelah Notion kita coret, Evernote dan Obsidian adalah kandidat yang sangat menarik (p.s blog post ditulis di Obsidian). Tapi kedua produk tersebut memiliki fungsi utama sebagai pencatat (*notetaker*). *That's it*. Markdown file yang disimpan ke dalam sebuah folder. *That's it, and it works for notetaking*.


![[Pasted image 20260712190538.png]]
URL yang tersimpan ketika menggunakan web clipper akan berbentuk file markdown. Ini ketidaknyamanan minor dari sisi UX, selain itu Obsidian juga tidak memiliki fitur overview dari semua item yang ada dalam sebuah folder. *Everything is a note* dan mengubah konvensi tersebut bukan pilihan (mungkin ada opsi community plugin, *but it's very likely to break and is painful to setup*).

--- 
Setelah menanyakan kebutuhan produk yang kujelaskan ke LLM (dalam hal ini [ChatGPT](https://chatgpt.com/share/6a51b41b-0eb4-83ec-8a52-54e6a45a05d5)), beberapa referensi menarik yang diberikan antara lain: 
1. **Bookmark managers**: Instapaper, Raindrop.io, Pocket
2. **Visual Asset Managers**: Eagle, PureRef, Adobe Bridge
3. **Personal Knowledge Management (PKM)**: Notion, Logseq, Obsidian
4. **Creative Research Platforms**: Are.na, Cosmos, Milanote, Fabric

Bookmark managers dan visual asset managers tentu aku coret, sangat terbatas dari segi fitur: hanya terfokus pada satu format item — URL atau asset visual saja. Dan *personal knowledge management* seperti Notion dan Obsidian terlalu overkill serta perlu konfigurasi khusus — dan itu pun masih kurang dalam memberikan pengalaman pengguna yang natural dan intuitif. 

Solusi pada *creative research platforms* sangat mendekati permasalahan yang coba kita selesaikan:
- Misalnya **[Cosmos](https://www.cosmos.so/)**, secara sekilas memiliki *use case* yang sangat mirip dengan Pinterest, yaitu sebagai platform pencari referensi dan inspirasi visual. Beberapa fitur yang menarik perhatianku: "Hide AI Content" dan "Search by Color". UI-nya juga elegan, minimalis dan terlihat sangat intuitif. Meski tertarik dengan konsep produk tersebut, aku tidak mencobanya secara langsung karena ini jelas bukan yang aku cari. 
- **[Milanote](https://milanote.com/)** menggunakan konsep *infinite canvas* sebagai inti dari produk mereka. Sangat berguna untuk bekerja dengan berbagai macam *resource* dan melihat koneksinya secara visual. Lagi-lagi: menarik, tapi bukan yang aku butuhkan. 
- [**Fabric**](https://fabric.so/) memiliki fitur yang persis aku butuhkan: penyimpanan multfiformat yang teroganisir dalam satu folder. ![[Pasted image 20260711160957.png]]
- Sama halnya dengan [**Are.na**](https://www.are.na/)  , bisa aku sederhanakan bahwa Are.na sama seperti Pinterest, namun bisa digunakan untuk menyimpan item dengan format lain, selain gambar. ![[Pasted image 20260711174229.png]]

**Are.na** dan **Fabric** adalah produk cukup baik jika hanya dinilai pada kemampuannya untuk mengorganisir file multiformat. Namun aspek penting lainnya juga menentukan pengguna untuk menggunakan dan tetap bertahan dengan sebuah produk, seperti: *pricing*, *privacy concern*, *user interface/experience*, *AI integration* dan lainnya. 

Kalaupun aku akan menggunakan aplikasi untuk merangkum *resource* dalam multiformat, aku menginginkan aplikasi tersebut memiliki desktop support (bukan browser) dan dapat digunakan tanpa memerlukan *Sign In* atau *Sign Up* (*probably too much to ask)*. Desktop support sangat penting bagiku. Selain karena kenyamanan, aku juga memiliki kontrol atas file tersebut secara langsung di komputerku. 

**Akses desktop dengan penyimpanan lokal lebih jauh kuinginkan daripada akses browser dengan penyimpanan cloud**

***Obsidian does this job exceptionally well for notetaking and that's why I love it*.** 

Notion boleh memiliki pilihan untuk mengintegrasikan berbagai AI agents ke *knowledge base* dan menampilkannya dalam dashboard dengan metrik macam-macam, tapi Obsidian lebih membantu tujuanku dalam menulis dan merorganisasi serta mengkoneksikan tulisan. 

> *Needless to say,  I need something to like Are.na & Fabric but with a desktop support and local storage-first like Obsidian. And if possible, No AI*. 
> 
> *Shorter version: Are.na or Fabric with Obsidian UX and file control* 

--- 
2026-07-12 12:53

Sebelum kita lanjut terlalu jauh, aku penasaran:  apakah proses/metode pembuatan produk pada zaman sebelum AI masih relevant? Apakah *Design Thinking* masih diperlukan? 

*Anyway.*
## Sketching the solution

Aku percaya bahwa shipping 10 produk setengah matang dalam dalam sebulan jauh lebih baik daripada shipping 1 produk matang dalam 1 bulan.

> *I prefer quantity and volume over quality. I believe in bias towards action.* 

Maka dari itu aku langsung memulai pengembangan dengan men-sketsa beberapa layar utama yang menjadi main flow. Untuk sementara, produknya akan aku namakan: Kuskus (jangan tanya kenapa)

Journey map yang aku bayangkan kurang lebih seperti ini: 
1. User sedang scrolling dan menjelajahi konten internet
2. User menemukan ada post Reddit menarik (misalnya) 
3. User menyimpan post tersebut
4. Post tersimpan sebagai link dalam inbox di penyimpanan lokal

Obsidian fixed this dengan web clipper untuk menyimpan link dan artikel, oleh karena itu kita gabungkan dengan solusi existing seperti Are.na dan Fabric terkait cara mereka menampilkan konten yang tersimpan (belakangan aku nemu [mymind](https://mymind.com/), basically UX-nya kurang lebih sama tapi lebih punya personality).
![[Pasted image 20260712190812.png]]
![[Pasted image 20260712190752.png]]

Setelah nyakar-nyakar di [Excalidraw](https://excalidraw.com/#json=LbQvTMWjflk4XXTotiISI,0M8JbXl_7Qjq7PSxRBaTLw), aku dapat gambaran kasar UInya dan beberapa referensi visual dari produk lain. Now let's start building the UI. 

## Proto-MVP
Before we code, let's focus on the tech specs