# SCA
Welcome to SOME CHESS APP {SCA} beta.

This app allows you to create PGN files where your engine plays against a database. At present you can select any or all of the following databases: The Master Database from LICHESS; The Online Database from LICHESS or most importantly the PLAYER Database from LICHESS. 

Effectively this allows you to prepare against a specific opponent using their lichess database.

INSTALATION: 
1)	Download the contents, ie. MasterConfig.txt and SCA_xxxx__.jar from here and place it in a folder on your pc.
2)	Download your engine of choice. I suggest Stockfish which can be downloaded from: https://stockfishchess.org/download/. Please make sure to download the version that is compatible with your PC and opperating system. If you unsure just double click the binary that you downloaded. It should open a black window and it should not close by itself. Place the engine in the same folder as the other two files. RENAME THE ENGINE TO: "Engine.exe"
3)	Change the settings as described below.
4)	Double click the SCAxxx___.jar file and read the output as it performs it work. If this does not start the program please make sure that you have java installed on your PC. This is done by opening a terminal and typing 'java --version'. If it gives ''java' is not recognized as an internal or external command,
operable program or batch file.' Then you need to install java first. TO do this you can follow this guide: https://phoenixnap.com/kb/install-java-windows
5)	After it is finished you will see 2 new files. The first file is the _log text file that give more detail of what lines SCA considered ect. The second file is the PGN that you can import to Lichess as a study.

SETTINGS:


You have full control over what and how many different lines will be looked at. Currently you have to change these settings in the MasterConfig.txt file but a GUI will soon be introduced. 
To change the settings simply open the file in notepad, change, save and run the app. Below is a very brief description of each of the settings:
1) Pgn_Name= My_SCA_Study -> Simply type the desired name for your PGN 
2) Starting_Pgn= 1. e4 e5 2. Nf3 -> Simply type the starting position from where you want SCA to start. Please note that you must always END THE LINE WITH YOUR MOVE. Therefore, if you leave it blank it will believe we are black and start with villain to make the first move. I you leave it after 1. e4 e5 2. Nf3 it will start with villain to make move 2 for black. 
3) Engine_Enable= true -> This is to enable stockfish evaluations. At present this is needed.
4) Cpu_Cores = 1 -> This value is how many CPU cores you want to assign to the engine. It is the same setting as that you will find on lichess as cpu’s. Please make sure that you do not set more than you have because then your PC will become unresponsive. 
Engine_Memory = 1024 -> This is the value of how much memory you want to allocate to the engine. It is the same setting as the “Memory” setting for the engine on lichess except it is not capped. Please make sure that you do not set more than you have because then your PC will become unresponsive.
Engine_Depth= 30 -> This is how deep you want the engine to search for your moves. The smaller the quicker the results but less reliable. The suggested value is between 30 and 40 depending on your hardware and your time. 
5)  Villain_Database_Enabled= true -> This simply asks whether you wish to use a specific player’s database to prepare against.
Villain_DB_Branches = 1 -> This is how many moves should be considered on each turn. The MAX is 10. This is like when you have opened the database and it gives all the different moves that were played in the particular position ie. 1. e4, 1. d4,1. c4, 1. Nf3….ect. This setting tells SCA how many of those options should be looked at on every turn. PLEASE NOTE THAT THIS SETTING DETERMINES HOW BIG THE PGN WILL BE AND IS COMULATIVE BETWEEN ALL THE DATABASES.
6)  Villain_Lichess_Username = German11 -> this is the user name of the person we want to prepare against.
7)  Villain_DB_Move_Total_Games= 1 ->  This setting will allow us to exclude positions which have not been played much. Ie. if we working from the stating position and villain has played 1. D4 500 times and 1. D3 only 1 time and no other moves then that d3 line will not be included even if the Branches setting was 2 or more.
8)  Villain_DB_Move_Popularity= 10 - > this is the % time that a move was played. Ie. if in a specific sharp position villain has played only Bxf7+ {95% of the time) and Nxf7 (4% of the time} and some other moves. SCA will not consider Nxf7 even if the branches setting was 2 or more and even if it was played more that the setting above.
9)  Villain_DB_Time_Control = ultraBullet,bullet,blitz,rapid,classical,correspondence -> This setting is obvious. However please note that all the letters are lowercase except the “B” in ultraBullet
10)  Online_Database_Enabled = true -> This will include lines from the normal lichess database.
11)  Online_DB_Branches = 1 -> See notes to the Villain DB 
12)  Online_DB_Move_Popularity= 1 -> See notes to the Villain DB 
13)  Online_DB_Move_Total_Games= 10 -> See notes to the Villain DB 
14)  Online_DB_Ratings = 1600,1800,2000,2200,2500 -> This is the same settings as on lichess.
15)  Online_DB_Time_Control = ultraBullet,bullet,blitz,rapid,classical,correspondence  -> See notes to the Villain DB 
16)  Master_Database_Enabled= true -> This will include lines from the master database.
17)  Master_DB_Branches = 2 -> This is how many moves out of the master database base will be included on every move.
18)  Cloud_Engine_Enable = true -> This is a performance enhancement feature. It will allow the user to use the cloud evaluations in stead of the engine evaluation to save time. 
19)  Cloud_Engine_Depth= 26 -> This is the minum depth for our cloud evaluation to be used.
20)  Line_Depth = 10 -> This is the maximum depth we want to prepare. 
21)  Need_To_Win = Need To Win -> This setting is not yet functional. It will allow the user to set whether we playing for a win at all costs or whether all we need is a draw. 
22)  Blunder_Stop= 80 -> This setting is not yet functional. It will allow user to stop lines after villain has blundered.
23)  License= beta


LEGAL STUFF
Notwithstanding what is stated below, the rights to this code remain with myself as the author thereof. You are only licenced to use it for the intended purpose and for the expressed duration.
Save as stated below, this code includes no code bellowing to any other party or subject to any other license.
The code includes one public repository which can be found here: https://github.com/bhlangonijr/chesslib and is available upon request. The master branch was used. That code is subject to the standard Appache License 2.0 which can be found here: https://github.com/bhlangonijr/chesslib/blob/master/LICENSE. The license file is available upon request and will be included once SCA get published.
 

