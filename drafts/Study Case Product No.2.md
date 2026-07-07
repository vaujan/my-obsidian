## _Note for writer, ignore this
1. **Problems**: What problems am I  getting? (Scratching my own itch)
2. **Validate Problems:** Are these problems occur in other people's lives? (Is there a demand? Is the pain any real and is the product really wanted?)
3. Is there already a cure? 
	1. If yes, how and why it works? 
	2. What can be improved from such products? 
4. Apa yang bisa kita tawarkan? Apakah mampu bagi kita untuk bersaing? 
5. Strategi untuk mendapat 'pengguna' pertama -> Open source-ing core features
6. Strategi untuk monetisasi -> Additional benefits for paid users
7. How these strategy works? We'll find out after 1 month of launching
8. Report
---
# Study Case: Multiformat Saver for Archiving the Web
# Problems
Menyimpan konten internet sejatinya cukup mudah. Fitur bookmarking konvensional yang berada pada browser menyelesaikan permasalahan ini jauh sebelum aplikasi notetaking seperti Notion, Obsidian, dan Evernote dengan plugin web clipper mereka masing-masing.

Tetapi ada gap yang cukup menyita perhatianku sebagai *[product builder](https://vaujan.github.io/)*. Yaitu tidak adanya sistem penyimpanan yang cukup fleksibel untuk berbagai macam format seperti gambar, teks, dan URL. 
## Mencari Sistem Penyimpan Multiformat
Sebagai contoh, ketika kita menemukan sebagai video di YouTube, mudah untuk menyimpannya: dengan web clipper contohnya. 

![[Pasted image 20260707114148.png]]

Akan tetapi, bagaimana jika yang ingin kita simpan adalah *screenshot* komponen UI untuk dijadikan inspirasi (semisal screenshot search bar pada YouTube) atau *reference board*? Bagaimana jika screenshot tersebut ingin kita simpan dalam satu folder yang sama dengan URL, dan teks file lain?

![[Pasted image 20260707140514.png]]

Secara sekilas, tidak ada solusi *out-of-the-box* yang muncul sebagai *top-of-mind*. Mungkin Notion. Notion memillki kapabilitas menyelesaikan permasalahan ini, namun dengan konfigurasi dan kustomisasi yang tentu memerlukan pengetahuan dasar tentang aplikasi tersebut. Lagi pula, Notion lebih cocok digunakan pada kasus pengembangan *knowledge base* atau *second brain* yang menginginkan fleksibiltas maksimal. Fleksibilitas yang menjadi nilai plus terbaik Notion juga sekaligus menjadi titik terlemahnya: yaitu tidak ada *out-of-the-box experience* dan sangat mudah untuk tergelincir pada *neraka konfigurasi*.

Menggunakan Notion dalam kasus ini seperti membunuh kecoak menggunakan *bazooka*. (*It's overkill*)

> [!NOTE] Catatan menarik mengenai use case Notion
> 
 >["This is configuration hell. Sharpening your axe until there is no axe left to sharpen and the tree you were going to fell has already rotted away".](https://kami.bearblog.dev/configuration-hell/)
>  
>  ["Notion is not a productivity tool. Notion is a tool for feeling productive while accomplishing nothing."](https://ilikekillnerds.com/2026/01/20/notion-is-where-productivity-goes-to-die/) 

Setelah Notion kita coret, Evernote dan Obsidian adalah kandidat yang sangat menarik (p.s blog post ditulis di Obsidian). Tapi kedua app tersebut memiliki fungsi utama sebagai pencatat (notetaking). *That's it*. Markdown file, text file -- yang disimpan ke dalam sebuah folder. 

![[Pasted image 20260707140429.png]]

URL yang tersimpan ketika menggunakan web clipper, browser extension resmi resmi dari Obsidian, akan berbentuk file markdown. Selain dari ketidaknyamanan *minor* dari sisi UX, Obsidian juga tidak memiliki fitur overview dari semua item yang ada dalam sebuah folder. 