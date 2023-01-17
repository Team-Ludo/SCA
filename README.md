# SCA
Welcome to SOME CHESS APP {SCA} beta.

This app allows you to create a PGN for purposes of preparing against an opponent or even against a database. 

SCA starts from a user defined position and then retrieves candidate move(s) for the villain from the database(s) as defined by the user. The number of moves so retrieved are included or limited by (i) which database(s) are used; (ii) how many branches are defined; (iii) the minimum games and popularity settings {these features can be seen below in the description of the settings}. 

Thereafter, and for each of the included villain moves, the app will search for a Hero move. The following options are available: (i) retrieve the moves Hero has played in a specific position then select the best performing move (*) as defined by our results; (ii) Use the most popular move from the master database; (iii) Use the best performing move (*) against the online database; (iv) Use the best performing move (*) against the villain’s database; (V) use the top engine move. Please note that if the App was unable to find any moves by way of the selected database, then it will automatically default to the top engine move. (*) The user can define what is considered the best performing move by electing to include or exclude draws. This is done in the Need to Win setting as described below. Should the user select more than one of the above options then the application will use the first selected option. All of these settings will be described under the settings chapter below.

INSTALATION: 

1)	Download the contents, ie. config.txt, readme and SCA_xxxx__.exe from here and extract it to a folder on your pc. 
2) You may need to download 7-zip to extract these files. If you need to do this you can go to https://www.7-zip.org/download.html and download the version compatible with your operating system. 
3)	Download your engine of choice. I suggest Stockfish which can be downloaded from: https://stockfishchess.org/download/. Please make sure to download the version that is compatible with your PC and operating system. If you are unsure just double click the binary that you downloaded. It should open a black or terminal window and it should not close by itself. If it does close by itself download an older version. Place the engine in the same folder as the other two files. RENAME THE ENGINE TO: "Engine.exe"
4)	Double click the SCAxxx___.exe file. This will launch a GUI {graphical user interface} where you can change the settings. 
5) After you have changed the settings just press run and read the output as it performs its work. 
6)	After the App has finished you will see 2 new files. The first file is the _log text.txt file that gives more detail of what lines SCA considered ect. The second file is the PGN that you can import to Lichess as a study.

SETTINGS:


You have full control over what and how many different lines will be looked at. These settings may be changed in the GUI. 
1) Pgn_Name= -> Simply type the desired name for your PGN. Please note that the log file for this run will also be named accordingly. 
2) Starting_Pgn= -> Simply type the starting position from where you want SCA to start. Please note that you must always END THE LINE WITH YOUR MOVE. Therefore, if you leave it blank it will believe we are black and start with villain to make the first move. Eg. if you leave it after 1. e4 e5 2. Nf3 it will start with villain to make move 2 for black. 
3) Engine_Enable= -> This is to enable stockfish evaluations for blunder checks. Please note that engine evaluations will occur automatically if no Hero move was found by any other means. 
4) Cpu_Cores = -> This value is how many CPU cores you want to assign to the engine. It is the same setting as that you will find on lichess as cpu’s. Please make sure that you do not set more than you have because then your PC will become unresponsive. 
5) Engine_Memory = -> This is the value of how much memory you want to allocate to the engine in MB. It is the same setting as the “Memory” setting for the engine on lichess except it is not capped. Please make sure that you do not set more than you have because then your PC will become unresponsive.
Engine_Depth= -> This is how deep you want the engine to search for your moves. The smaller the quicker the results but less reliable. The suggested value is between 30 and 40 depending on your hardware and your time. 
6)  Villain_Database_Enabled= -> This simply asks whether you wish to use a specific player’s database to prepare against. If enabled the App will do a search for your opponent’s moves according to the settings below. 
7) Villain_DB_Branches = -> This is how many moves should be considered on each turn. The MAX is 10. This is like when you have opened the database and it gives all the different moves that were played in the particular position ie. 1. e4, 1. d4,1. c4, 1. Nf3….ect. PLEASE NOTE THAT THIS SETTING DETERMINES HOW BIG THE PGN WILL BE AND IS COMULATIVE BETWEEN ALL THE DATABASES. 
8)  Villain_Lichess_Username = -> this is the username of the person we want to prepare against.
9)  Villain_DB_Move_Total_Games= -> This setting will allow us to exclude positions which have not been played much. Ie. if we working from the stating position and villain has played 1. d4 500 times and 1. d3 only 1 time and no other moves then that d3 line will not be included even if the Branches setting was 2 or more. This will exclude mouse slips.
10)  Villain_DB_Move_Popularity= - > this is the % time that a move was played. Ie. if in a specific sharp position villain has played only Bxf7+ {95% of the time) and Nxf7 (4% of the time} and some other moves. SCA will not consider Nxf7 even if the branches setting was 2 or more and even if it was played more that the setting above.
11)  Villain_DB_Time_Control = -> This setting is obvious. However please note that all the letters are lowercase except the “B” in ultraBullet. Please make sure to formulate this setting properly it is the cause of many crashes. 
12)  Online_Database_Enabled = -> This will include lines from the normal lichess online database. We can use this if we want to “create a repertoire” against our online opponents or if we want to widen our preparation against an opponent to include popular moves outside of their normal repertoire.
13)  Online_DB_Branches = -> See notes to the Villain DB 
14)  Online_DB_Move_Popularity= -> See notes to the Villain DB 
15)  Online_DB_Move_Total_Games= -> See notes to the Villain DB 
16)  Online_DB_Ratings = -> This is the same settings as on lichess. Please note that the options changed January 2023.
17)  Online_DB_Time_Control = -> See notes to the Villain DB 
18)  Villian_Master_Database_Enabled= -> If set true then the app will include moves from the master database of lichess as candidate moves for Villain. 
19)  Master_DB_Branches = -> This is how many moves out of the master database base will be included on every move as candidate moves for Villain. 
20)  Hero_Master_Database_Enabled= -> If set true then the app will include moves from the master database of lichess as candidate moves for Hero. 
21) Hero_Database_Enabled= -> If set true then the app will select the Hero move from the Hero’s database on lichess. 
22)  Hero_DB_Branches = -> This is how many candidates moves out of the Hero database base will be considered for the selection described above. 
23)  Hero_Lichess_Username = -> Our username on lichess.
24)  Villain_Worse_Moves_Enabled -> If set to true the App will select the best performing move against villain database for Hero. As defined by the statistics and calculated in accordance with the Need to win setting.  Please note that it will only consider the number of candidates as defined in the Villain_DB_Branches setting.
25)  Online_Best_Move_Enabled -> If set to true the App will select the best performing move against the online database for Hero.  As defined by the statistics and calculated in accordance with the Need to win setting.  Please note that it will only consider the number of candidates as defined in the settings above for the online database.

22)  Cloud_Engine_Enable = -> This is a performance enhancement feature. It will allow the user to use the cloud evaluations instead of the engine evaluation to save time. This feature will make SCA substantially faster for the first couple of moves. The benefit decreases the deeper the lines go for obvious reasons.
19)  Cloud_Engine_Depth= -> This is the lowest depth for our cloud evaluation to be used.
20)  Line_Depth = -> This is the maximum depth we want to prepare. 
21)  Need_To_Win = -> This setting will be used to determine which moves to use as Hero moves based on statistics. If set to true then only the win rate will be taken into account. If set to false then draws will be included as “wins”. Ie. if a move has 33% wins, 33% draws and 33% loses then a setting of true will give a “winrate” of 33% and a setting of false will give a “winrate” of 66%. 
22)  Blunder_Stop= 80 -> This is the maximum amount of centipawn we are willing to lose to prefer a database move above the engine top move. This test will always be run if the engine is enabled. Please note that this feature substatially increase the time used to complete any run.
23)  License= beta



LEGAL STUFF
Notwithstanding what is stated below, the rights to this code remain with myself as the author thereof. You are only licensed to use it for the intended purpose of running the app in accordance with the readme file and for the expressed duration.
Save as stated below, this code includes no code belloning to any other party or subject to any other license.

The code includes one public repository which can be found here: https://github.com/bhlangonijr/chesslib and is available upon request. The master branch was used. That code is subject to the standard Appache License 2.0 which can be found here: https://github.com/bhlangonijr/chesslib/blob/master/LICENSE. The license file is available upon request and will be included once SCA get published.


