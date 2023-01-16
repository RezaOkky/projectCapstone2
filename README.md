# US YOUTUBE TRENDING

## LATAR BELAKANG MASALAH
Client yang merupakan seorang youtuber membutuhkan bantuan untuk mengetahui faktor apa saja yang dapat mempengaruhi algoritma youtube trending, informasi ini sangat membantu bagi client untuk dapat membuat video youtubenya menjadi trending.

Sebagai seorang Data Analis kita dihadapkan untuk menjawab pertanyaan berikut :


- Apakah terdapat korelasi antar variabel yang membuat video trending ?
- Apakah terdapat pengaruh jumlah likes terhadap jumlah views ?
- Apakah terdapat pengaruh jumlah komentar terhadap jumlah views ?
- Berapa lama yang dibutuhkan video yang baru dipublish untuk menjadi trending ?
- Channel Youtube mana yang paling banyak mempunyai video yang trending ?
- Kategori video mana yang mempunyai video trending paling banyak ?


## DATA
DATA CSV :

16 Kolom :
`video_id’,  `title`, `channel_title’, `category_id` , ` trending_date `, `publish_time`,  `tags`, `views` ,  `likes`,  `dislikes`, `comment_count`, `thumbnail_link` , `comments_disabled` , `ratings_disabled` , `video_error_or_removed`, `description`.

Index : 40949


DATA JSON :

Kolom :
`kind`, ‘etag’, ‘item’

Index : 40949


## Data Manipulation
- Membuat dataframe baru dari file json dengan kolom category.id dan category
- Menggabungkan data .json dengan data .csv 
- Mengganti tipe data kolom publish time dan trending date menjadi type datetime, kemudian membuat kolom baru publish date yang diambil dari data date di kolom publish time
- Membuat kolom baru Day To Trending yang berisi lama video tersebut trending dari tanggal publishnya
- Merubah type data kolom DayToTrending menjadi int untuk mempermudah analisa kedepannya


## Cleaning data
Null Value
- Terdapat 570 baris pada kolom description / 1,4%
- Mengganti null Value

Data Duplikat
- Terdapat 48 baris data duplikat
- Menghapus data duplikat dengan hasil dari 40949 baris menjadi 40901 baris

Outlier
- Terdapat 4497 baris data outlier
- Tidak menghapus data outlier


## Kesimpulan
- 'likes' mempunyai korelasi positif paling kuat dengan 'views' dengan nilai korelasi 0.85,  disusul 'dislikes' dengan nilai korelasi 0.47.'dayToTrending', 'title_length' 'tags_length' dengan korelasi negatif yang rendah pada  'views' nilai korelasi masing-masing -0.014, -0.036, -0.016
- Untuk Uji Hipotesis  antara variable Likes dan Comment Count terhadap Views dengan hasil keduanya menolak H0 yang berarti kedua variable tersebut memiliki pengaruh yang cukup kuat terhadap variable views
- Lama video untuk menjadi trending paling banyak kurang dari 7 hari dihitung dari dipublishnya video tersebut, dengan jumlah video lebih dari 25000 video. Tapi ada juga video menjadi trending lebih dari 1000 hari setelah video tersebut dipublish.
- Channel Youtube yang mempunyai video trending terbanyak adalah ESPN dengan jumlah video mencapai 200 lebih, disusul The Tonight Show Starring Jimmy Fallon, dan untuk views terbanyak terdapat di channel ChildishGambinoVEVO, diikuti ibighit dan Dude Perfect
- Untuk video yang trending, jam posting/publish time berdasar analisa paling banyak dilakukan pada pukul 14-17 

### Link Tableau

https://public.tableau.com/views/YoutubeTrending_16731659714810/Dashboard1?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link

