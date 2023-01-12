# SCA
Welcome to SOME CHESS APP {SCA} beta.

This app allows you to create PGN for purposes of preparing against an opponent or even against a database. 

SCA starts at a user defined position and then retrieves candidate move(s) for the villain from the database(s) as defined by the user. The number of moves so retrieved are included or limited by (i) which database(s) are used; (ii) how many branches are defined; (iii) the minimum games and popularity settings {these features can be seen below in the description of the settings}. 

Thereafter, and for each of the included villain moves, the app will search for a Hero move. The following options are available: (i) retrieve the moves Hero has played in a specific position then select the best performing move (*) as defined by our results; (ii) Use the most popular move from the master database; (iii) Use the best performing move (*) against the online database; (iv) Use the best performing move (*) against the villians database; (V) use the top engine move. Please note that if the App was unable to find any moves by way of the selected database then it will automatically default to the top engine move. (*) The user can define what is considered the best performing move by electing to include or exclude draws. This is done in the Need to Win setting as desribed below. All of these settings will be described under the settings chapter below.

INSTALATION: 
1)	Download the contents, ie. MasterConfig.txt and SCA_xxxx__.jar from here and place it in a folder on your pc. The MasterConfig.txt file is where you will change your desired settings and the SCA_XXX.jar file is the actual application. 
2)	Download your engine of choice. I suggest Stockfish which can be downloaded from: https://stockfishchess.org/download/. Please make sure to download the version that is compatible with your PC and operating system. If you unsure just double click the binary that you downloaded. It should open a black or terminal window and it should not close by itself. If it does close by it self download an older version. Place the engine in the same folder as the other two files. RENAME THE ENGINE TO: "Engine.exe"
3)	Change the settings as described below.
4)	Double click the SCAxxx___.jar file and read the output as it performs it work. If this does not start the program, please make sure that you have java installed on your PC. This is done by opening a terminal and typing 'java --version'. If it gives ''java' is not recognized as an internal or external command, operable program or batch file.' Then you need to install java first. TO do this you can follow this guide: https://phoenixnap.com/kb/install-java-windows. Make sure to install the java “JDK”.
5)	After the App has finished you will see 2 new files. The first file is the _log text.txt file that give more detail of what lines SCA considered ect. The second file is the PGN that you can import to Lichess as a study.

SETTINGS:


You have full control over what and how many different lines will be looked at. Currently you have to change these settings in the MasterConfig.txt file but a GUI will be introduced. 
To change the settings simply open the file in notepad, change, save and run the app. Below is a very brief description of each of the settings:
1) Pgn_Name= My_SCA_Study -> Simply type the desired name for your PGN 
2) Starting_Pgn= 1. e4 e5 2. Nf3 -> Simply type the starting position from where you want SCA to start. Please note that you must always END THE LINE WITH YOUR MOVE. Therefore, if you leave it blank it will believe we are black and start with villain to make the first move. I you leave it after 1. e4 e5 2. Nf3 it will start with villain to make move 2 for black. 
3) Engine_Enable= true -> This is to enable stockfish evaluations. At present this is needed. Please note that engine evaluations will occur automatically if no Hero move was found by any other means.
4) Cpu_Cores = 1 -> This value is how many CPU cores you want to assign to the engine. It is the same setting as that you will find on lichess as cpu’s. Please make sure that you do not set more than you have because then your PC will become unresponsive. 
5) Engine_Memory = 1024 -> This is the value of how much memory you want to allocate to the engine. It is the same setting as the “Memory” setting for the engine on lichess except it is not capped. Please make sure that you do not set more than you have because then your PC will become unresponsive.
Engine_Depth= 30 -> This is how deep you want the engine to search for your moves. The smaller the quicker the results but less reliable. The suggested value is between 30 and 40 depending on your hardware and your time. 
6)  Villain_Database_Enabled= true -> This simply asks whether you wish to use a specific player’s database to prepare against. If enabled the App will do a search for your opponents moves according to the settings below. 
7) Villain_DB_Branches = 1 -> This is how many moves should be considered on each turn. The MAX is 10. This is like when you have opened the database and it gives all the different moves that were played in the particular position ie. 1. e4, 1. d4,1. c4, 1. Nf3….ect. PLEASE NOTE THAT THIS SETTING DETERMINES HOW BIG THE PGN WILL BE AND IS COMULATIVE BETWEEN ALL THE DATABASES. 
8)  Villain_Lichess_Username = German11 -> this is the username of the person we want to prepare against.
9)  Villain_DB_Move_Total_Games= 1 -> This setting will allow us to exclude positions which have not been played much. Ie. if we working from the stating position and villain has played 1. d4 500 times and 1. d3 only 1 time and no other moves then that d3 line will not be included even if the Branches setting was 2 or more. This will exclude mouse slips.
10)  Villain_DB_Move_Popularity= 10 - > this is the % time that a move was played. Ie. if in a specific sharp position villain has played only Bxf7+ {95% of the time) and Nxf7 (4% of the time} and some other moves. SCA will not consider Nxf7 even if the branches setting was 2 or more and even if it was played more that the setting above.
11)  Villain_DB_Time_Control = ultraBullet,bullet,blitz,rapid,classical,correspondence -> This setting is obvious. However please note that all the letters are lowercase except the “B” in ultraBullet
12)  Online_Database_Enabled = true -> This will include lines from the normal lichess database. We can use this if we want to “create a repertoire” against our online opponents or if we want to widen our preparation against an opponent to include popular moves outside of their normal repertoire.
13)  Online_DB_Branches = 1 -> See notes to the Villain DB 
14)  Online_DB_Move_Popularity= 1 -> See notes to the Villain DB 
15)  Online_DB_Move_Total_Games= 10 -> See notes to the Villain DB 
16)  Online_DB_Ratings = 600,1000,1400,1600,1800,2000,2200,2500-> This is the same settings as on lichess.
17)  Online_DB_Time_Control = ultraBullet,bullet,blitz,rapid,classical,correspondence  -> See notes to the Villain DB 
18)  Villian_Master_Database_Enabled= true -> If set true then the app will include moves from the master database of lichess as candidate moves for Villain. 
19)  Master_DB_Branches = 2 -> This is how many moves out of the master database base will be included on every move as candidate moves for Villain. 
20)  Hero_Master_Database_Enabled= true -> If set true then the app will include moves from the master database of lichess as candidate moves for Hero. 
21) Hero_Database_Enabled= true -> If set true then the app will include moves from Hero database on lichess as candidate moves for Hero. 
22)  Hero_DB_Branches = 2 -> This is how many moves out of the Hero database base will be included on every move as candidate moves for Hero. 
23)  Hero_Lichess_Username = german11-> Our username on lichess.
24)  Villain_Worse_Moves_Enabled -> If set to true the App will select the best performing move against villain database for Hero.
25)  Online_Best_Move_Enabled -> If set to true the App will select the best performing move against the online database for Hero.
22)  Cloud_Engine_Enable = true -> This is a performance enhancement feature. It will allow the user to use the cloud evaluations instead of the engine evaluation to save time. 
19)  Cloud_Engine_Depth= 26 -> This is the lowest depth for our cloud evaluation to be used.
20)  Line_Depth = 10 -> This is the maximum depth we want to prepare. 
21)  Need_To_Win = true -> This setting will be used to determine which moves to use as Hero moves based on statistics. If set to true then only the win rate will be taken into account. If set to false then draws will be included as “wins”. Ie. if a move has 33% wins, 33% draws and 33% loses then a setting of true will give a “winrate” of 33% and a setting of false will give a “winrate” of 66%. 
22)  Blunder_Stop= 80 -> This setting is not yet functional. It will allow user to stop lines after villain has blundered.
23)  License= beta



LEGAL STUFF
Notwithstanding what is stated below, the rights to this code remain with myself as the author thereof. You are only licenced to use it for the intended purpose and for the expressed duration.
Save as stated below, this code includes no code bellowing to any other party or subject to any other license.
The code includes one public repository which can be found here: https://github.com/bhlangonijr/chesslib and is available upon request. The master branch was used. That code is subject to the standard Appache License 2.0 which can be found here: https://github.com/bhlangonijr/chesslib/blob/master/LICENSE. The license file is available upon request and will be included once SCA get published.
 

