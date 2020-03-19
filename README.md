# KECERDASAN BUATAN - F

Muhammmad Daffa' Aflah Syarif - 05111840000030

Teknik Informatika - Fakultas Teknologi Elektro & Informatika Cerdas

Institut Teknologi Sepuluh Nopember Surabaya

# 1. 8 Queen - Hill Climbing
Source Code : [8queen-hill-climbing.cpp](https://github.com/daffaaflah6/KB-F_05111840000030/blob/master/8%20queen%20-%20hill%20climbing/n-queen.cpp)

# 2. 4 Queen - CSP (Constraint Satisfaction Problems)
Source Code : [4queen-csp.cpp](https://github.com/daffaaflah6/KB-F_05111840000030/blob/master/4%20queen%20csp/n-queen_csp.cpp)

# 3. 8 Puzzle
Source Code : [8puzzle.cpp](https://github.com/daffaaflah6/KB-F_05111840000030/blob/master/8%20puzzle/8-puzzle.cpp)

# 4. 8 Puzzle - BFS (Breadth First Search)
Source Code : [8puzzle-bfs.cpp](https://github.com/daffaaflah6/KB-F_05111840000030/blob/master/8%20puzzle%20bfs/8-puzzle_bfs.cpp)

# 5. 8 Puzzle - DFS (Depth First Search)

# 6. 8 Puzzle - IDS (Iterative Deepening Search)

# 7. 8 Puzzle - Heuristic
8-Puzzle merupakan salah satu jenis permainan puzzle dimana kita harus mencapai goal puzzle dari initial puzzle yang diberikan. Untuk mencapai goal puzzle, 8-puzzle ini menyediakan satu grid kosong agar grid-grid lain disekitarnya dapat digerakkan. Sebagai contoh Inisial State dan Goal State dari sebuah puzzle adalah :

![8ph](https://user-images.githubusercontent.com/52326074/77028971-f9001b00-69cc-11ea-9301-6be95c8f1df1.PNG)

Pada pembahasan kali ini, saya ingin menyelesaikan puzzle ini dengan suatu algoritma, yaitu Algoritma Greedy, dengan menggunakan dua fungsi heuristik. Algoritma Greedy merupakan algoritma yang sederhana dan lempeng (straightforward). Secara harfiah greedy artinya rakus atau tamak.

Algoritma Greedy membentuk solusi langkah per langkah. Terdapat banyak pilihan yang perlu dieksplorasi pada setiap langkah solusi. Oleh karena itu, pada setiap langkah harus dibuat keputusan yang terbaik dalam menentukan pilihan. 

Dalam bahasan ini, fungsi heuristik yang akan kita tampilkan yaitu adalah sebagai berikut.
- h₁(n) : sebagai banyak grid yang menempati tempat yang salah.
- h₂(n) : sebagai total keseluruhan jarak tiap grid yang menempati tempat yang salah terhadap posisi grid yang benar, atau sering disebut dengan manhattan distance.

Solusi Penyelesaian dengan fungsi Heuristik Pertama yaitu banyak grid yang menempati tempat yang salah

![8puzzle-heuristic1.1](https://user-images.githubusercontent.com/52326074/77029102-58f6c180-69cd-11ea-9571-7a69fe89de7d.PNG)
![8puzzle-heuristic1.2](https://user-images.githubusercontent.com/52326074/77029100-585e2b00-69cd-11ea-8d32-03512709f26c.PNG)
![8puzzle-heuristic1.3](https://user-images.githubusercontent.com/52326074/77029097-572cfe00-69cd-11ea-845e-7e8b50514214.PNG)

Solusi :
Initial State -> Right -> Up -> Right -> Down -> Down -> Left -> Up -> Right -> Down(Goal)

Solusi Penyelesai dengan fungsi Heuristik Kedua yaitu total keseluruhan jarak tiap grid yang menempati tempat yang salah terhadap posisi grid yang benar, atau sering disebut dengan manhattan distance.

![8puzzle-heuristic2.1](https://user-images.githubusercontent.com/52326074/77029181-8f344100-69cd-11ea-9799-24cda528fdd5.PNG)
![8puzzle-heuristic2.2](https://user-images.githubusercontent.com/52326074/77029178-8e9baa80-69cd-11ea-9d35-2282c1916e48.PNG)
![8puzzle-heuristic2.3](https://user-images.githubusercontent.com/52326074/77029175-8d6a7d80-69cd-11ea-8775-2fd302b4ad62.PNG)

Solusi :
Initial State -> Right -> Up -> Right -> Down -> Down -> Left -> Up -> Right -> Up(Goal)


Kesimpulannya, dari semua yang telah dipaparkan diatas, penggunaan dari dua fungsi heuristik Algoritma Greedy pada solusi penyelesaian 8-puzzle, baik fungsi heuristik pertama dan kedua sama sama mampu memberikan solusi penyelesaian dari awal state sampai ke goal state. Tetapi menurut pendapat saya, pada penggunaan fungsi heuristik pertama jumlah State puzzle yang memiliki fungsi heuristik yang sama lebih banyak dari pada penggunaan fungsi heuristik kedua. Jadi, penggunaan solusi dari fungsi heuristik kedua dalam contoh penyelesaian 8-puzzle diatas lebih optimal dari pada fungsi heuristik pertama.

# 8. Minimax - Tic Tac Toe
Source Code : [minimax-tictactoe.cpp](https://github.com/daffaaflah6/KB-F_05111840000030/blob/master/Minimax%20tictactoe/minimax.cpp)

Tic Tac Toe merupakan permainan yang dimainkan oleh 2 pemain dengan menempatkan ‘buah’ yang berlainan untuk tiap pemain pada kotak 3 x 3. Penempatan ‘buah’ dilakukan secara bergantian sehingga salah satu pemain menjadi pemenang atau seluruh kotak terisi oleh ‘buah’. Salah satu pemain dikatakan menang jika dapat menempatkan ‘buah’ berjajar sebanyak 3 buah baik secara horisontal, vertikal atau diagonal.

Dalam permainan ini kita harus berusaha untuk memaksimalkan kemungkinan untuk mencapai kemenangan pemain pertama dan meminimalkan kemungkinan kemenangan lawan (pemain kedua).

Komponen penelusuran dalam aplikasi minimax pada permainan Tic Tac Toe ini adalah :

- `Initial state` merupakan keadaan saat pencarian akan dilakukan, pada saat permainan mulai dilakukan (jika pemain pertama jalan pertama), initial statenya adalah :

![tictactoe.1](https://user-images.githubusercontent.com/52326074/77034748-4dab9200-69dd-11ea-8215-48c660f28237.JPG)

Initial state selalu berubah saat giliran jalan pemain pertama.
- `Operator (rule/ilegal moves)`, Operator pada permainan ini adalah pemain dapat meletakkan ‘buah’ nya secara sembarang di kotak yang masih kosong.
- `Terminal Test` adalah keadaan dimana komposisi terbaik yang dilakukan pemain pertama setelah diadakan penelusuran.
- `Utility function` pada permainan ini adalah mencari kemungkinan kemenangan bagi pemain pertama dikurangi dengan kemungkinan kemenangan dari pemain lawan. Pada saat permainan dimulai masing-masing kemungkinan kemenangan tiap pemain adalah 8 yaitu 3 horisontal + 3 vertikal + 2 diagonal.

![tictactoe.2](https://user-images.githubusercontent.com/52326074/77034890-b561dd00-69dd-11ea-9a93-b8adca75b3e8.JPG)

Contoh pada komposisi :

![tictactoe.3](https://user-images.githubusercontent.com/52326074/77034911-c4488f80-69dd-11ea-904e-87b6294917db.JPG)

Kemungkinan kemenangan pemain pertama adalah 6, sedangkan kemungkinan kemenangan pemain kedua adalah 5.

![tictactoe.4](https://user-images.githubusercontent.com/52326074/77034938-d88c8c80-69dd-11ea-845c-596e936eaad9.JPG)

Jadi nilai untuk komposisi di atas adalah 6 – 5 = 1.

Dari keadaan permainan dimulai, graph minimax untuk Two-Ply Search dapat digambarkan sebagai berikut (X = pemain pertama, O = pemain kedua):

![tictactoe.5](https://user-images.githubusercontent.com/52326074/77034975-efcb7a00-69dd-11ea-97ae-2ff5b0943d04.JPG)

Nilai node E sampai P didapat dari utility function yang telah didefinisikan sebelumnya sehingga didapatkan :
E = 6 – 5 = 1
F = 5 – 5 = 0
G = 6 – 5 = 1
H = 5 – 5 = 0
I = 4 – 5 = -1
J = 5 – 4 = 1
K = 6 – 4 = 2
L = 5 – 6 = -1
M = 5 – 5 = 0
N = 5 – 6 = -1
O = 6 – 6 = 0
P = 4 – 6 = -2

Ada sembilan langkah yang mungkin dilakukan oleh pemain pertama karena kotak kosongnya berjumlah 9, tapi pada diagram diatas hanya diambil 3 kemungkinan (node B,C dan D), karena 6 kemungkinan lainnya setara dengan ke-3 komposisi di atas, misalnya :

![tictactoe.6](https://user-images.githubusercontent.com/52326074/77035007-083b9480-69de-11ea-9932-0b194195291b.JPG)

Dari node B seharusnya didapatkan node anak sebanyak 8 node, dengan mengabaikan node yang setara node anak dari B menjadi E, F, G, H dan I. Dengan cara yang sama didapatkan node anak dari C yaitu J dan K, sedangkan node anak dari D yaitu L, M, N, O dan P.
Karena hanya menggunakan Two-Ply Search, node-node anak dari B, C dan D dicari nilainya, kemudian dicari yang terkecil (min) masing-masing untuk dijadikan nilai B, C dan D. Selanjutnya dicari nilai terbesar (max) dari ketiga nilai tersebut untuk menentukan langkah pemain pertama.

Pada diagram yang digambarkan diatas, node anak dari B bernilai masing-masing E=1, F=0, G=1, H=0 dan I=-1 jadi nilai B diambil yang terkecil yaitu –1.

Node anak dari C bernilai masing-masing J=1 dan K=2 jadi nilai C diambil yang terkecil yaitu 1. Kemudian node anak dari D bernilai masing-masing L=-1, M=0, N=-1, O=0 dan P=-2 jadi nilai C diambil yang terkecil yaitu –2.
Selanjutnya dari nilai node B=-1, C=1, dan D=-2 diambil nilai terbesar yaitu C=1, yang berarti langkah terbaik yang harus dilakukan oleh pemain pertama adalah node C.

Setelah pemain kedua menempatkan buahnya, keadaan saat itu dijadikan initial state dan dilakukan kembali pelacakan dengan langkah yang telah dijelaskan di atas. Contoh : Misalkan pemain kedua meletakkan buahnya seperti gambar berikut :

![tictactoe.7](https://user-images.githubusercontent.com/52326074/77035046-21444580-69de-11ea-89a1-5eeb2dd345c4.JPG)

Dari keadaan ini, graph minimax untuk Two-Ply Search dapat digambarkan sebagai berikut (X = pemain pertama, O = pemain kedua):

![tictactoe.8](https://user-images.githubusercontent.com/52326074/77035066-2e613480-69de-11ea-816d-f67b069d2523.JPG)

Dari diagram diatas, langkah terbaik yang dapat dilakukan oleh pemain pertama terdapat dua pilihan yaitu B(1) dan D(1).

# 9. Wumpus World Game
