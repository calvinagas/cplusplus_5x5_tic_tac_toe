# 5X5 Tic Tac Toe using C++
## Descriptions

5X5 Tic Tac Toe Games (You vs Bot)

## Checkout below codes
``` c++ 
include <iostream.h>
#include <conio.h>
#include <stdlib.h>
#include <time.h>
#include "dos.h"



char dateStr [9], timeStr [9];                                                           




/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

void loading()                                                                      
{
	cout<<"\n\n\n\n\n\n\n\n\n\n";
   cout<<"\t                       >> loading.... "<<endl;
}

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

void hvd()
{
   cout<<"\n\n";                                                                        
   cout<<"\n\t-----    -----   ------                ------   -------------        ";
   cout<<"\n\t-----    -----    ------              ------    ---------------       ";
   cout<<"\n\t-----    -----     ------            ------     ----        -----     ";
   cout<<"\n\t--------------      ------          ------      ----         ----     ";
   cout<<"\n\t--------------       ------        ------       ----         ----     ";
   cout<<"\n\t--------------        ------      ------        ----         ----     ";
   cout<<"\n\t-----    -----         ----------------         ----        -----     ";
   cout<<"\n\t-----    -----          --------------          ----------------      ";
   cout<<"\n\t-----    -----           ------------           --------------        ";
   cout<<"\n";
   cout<<"\n\t==============      ======================      =================     ";
   cout<<"\n\t==============      ======================      =================     ";
   cout<<"\n\n\n\t\t\t\       -> Press 'Enter' <-";
   cout<<"\n\n\n\t\t\t\t\ ";
}

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

void display_ending()
{
   cout<<"\n";                                                                         
   cout<<"\t\t\t     ======================    "<<endl;
   cout<<"\t\t\t      &  &   &    &   &&&      "<<endl;
   cout<<"\t\t\t      &&&&    &  &    &  &     "<<endl;
   cout<<"\t\t\t      &  &     &&     &&&      "<<endl;
   cout<<"\t\t\t     ======================    "<<endl;
   cout<<"\n\n";
   cout<<"\t\t\t    Thank"<<endl;
   sleep(1);
   cout<<"\t\t\t\t\t     You"<<endl;
   sleep(1);
   cout<<"\t\t     For"<<endl;
   sleep(1);
   cout<<"\t\t\t     Playing!!"<<endl;

}

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


char blockOne = 'a';                                                                    //at first_option(blockOne initialize to 'a')
char blockTwo = 'b';                                                                    //at first_option(blockTwo initialize to 'b')
char blockThree = 'c';                                                                  //at first_option(lockThree initialize to 'c')
char blockFour = 'd';                                                                   //at first_option(blockFour initialize to 'd')
char blockFive = 'e';                                                                   //at first_option(blockFive initialize to 'e')
char blockSix = 'f';                                                                    //at first_option(blockSix initialize to 'f')
char blockSeven = 'g';                                                                  //at first_option(blockSeven initialize to 'g')
char blockEight = 'h';                                                                  //at first_option(blockEight initialize to 'h')
char blockNine = 'i';                                                                   //at first_option(blockNine initialize to 'i')
char blockTen = 'j';                                                                    //at first_option(blockTen initialize to 'j')
char blockEleven = 'k';                                                                 //at first_option(blockEleven initialize to 'k')
char blockTwelve = 'l';                                                                 //at first_option(blockTwelve initialize to 'l')
char blockThirteen = 'm';                                                               //at first_option(blockThirteen initialize to 'm')
char blockFourteen = 'n';                                                               //at first_option(blockFourteen initialize to 'n')
char blockFifteen = '#';                                                                //at first_option(blockFifteen initialize to '#')
char blockSixteen = 'p';                                                                //at first_option(blockSixteen initialize to 'o')
char blockSeventeen = 'q';                                                              //at first_option(blockSeventeen initialize to 'q')
char blockEighteen = 'r';                                                               //at first_option(blockEighteen initialize to 'r')
char blockNineteen = 's';                                                               //at first_option(blockNineteen initialize to 's')
char blockTwenty = 't';                                                                 //at first_option(blockTwenty initialize to 't')
char blockTwentyOne = 'u';                                                              //at first_option(blockTwentyOne initialize to 'u')
char blockTwentyTwo = 'v';                                                              //at first_option(blockTwentyTwo initialize to 'v')
char blockTwentyThree = 'w';                                                            //at first_option(blockTwentyThree initialize to 'w')
char blockTwentyFour = '+';                                                             //at first_option(lockTwentyFour initialize to '+')
char blockTwentyFive = 'y';                                                             //at first_option(blockTwentyFive initialize to 'y')

int computerRandomPick;                                                                 //random location which computer selects if first.
int computerPick;                                                                       //used to decide computer vs player AI moves.
char playerChoice;
bool playerTurn;
int gameWin = 3;
                                                                                        
                                                                                        //random starting turn chooser
int turnFirst;                                                                          //variable to decide whoever goes first

char firstPlayer[100];                                                                  //at second_option an character array size 100 that stored firstplayer name
char secondPlayer[100];                                                                 //at second_option an character array size 100 that stored secondplayer name


void player_turn();
bool gameover();
char turn;
bool draw = false;
char board[5][5] = {{'a', 'b', 'c', 'd', 'e'},                                          //at second_option - The 2Dimensional array that stored the character with row at size 5 and column at size 5
						  {'f', 'g', 'h', 'i', 'j'},
                    {'k', 'l', 'm', 'n', '#'},
                    {'p', 'q', 'r', 's', 't'},
                    {'u', 'v', 'w', '+', 'y'}};


void display_board(char board[][5])                                                     //parameter passing by reference
{                                                                                       //at second_option - To display the 5X5 table which is refers to the board
  	cout<<"\n";
  	cout<<"\t\t\t     ======================    "<<endl;
  	cout<<"\t\t\t      &  &   &    &   &&&      "<<endl;
  	cout<<"\t\t\t      &&&&    &  &    &  &     "<<endl;
  	cout<<"\t\t\t      &  &     &&     &&&      "<<endl;
  	cout<<"\t\t\t     ======================    "<<endl;
  	cout<<"\n\n";

  		_strdate( dateStr),   //to display the current date
  		_strtime( timeStr);   //to display the current time

  	cout<<"\tDate: "<<dateStr<<"\t\t\t\t\t   Time: "<<timeStr;
  	cout<<endl;
  	cout<<"\n\n";
  	cout<<"\t\t\t-------------------------------\n";

  	for (int x=0; x<5; x++)
  	{
   	cout<<"\t\t\t|";
   		for(int y=0;y<5;y++)
   		{
    			cout<<"  "<<board[x][y]<<" ||";
   		}
   		cout<<"\n\t\t\t-------------------------------"<<endl;
  	}
}



/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

void gameBoard()                                                   
{
	  cout<<"\n";
    cout<<"\t\t\t     ======================    "<<endl;
    cout<<"\t\t\t      &  &   &    &   &&&      "<<endl;
    cout<<"\t\t\t      &&&&    &  &    &  &     "<<endl;
    cout<<"\t\t\t      &  &     &&     &&&      "<<endl;
    cout<<"\t\t\t     ======================    "<<endl;
    cout<<"\n\n";
    _strdate( dateStr),
    _strtime( timeStr);
    cout<<"\tDate: "<<dateStr<<"\t\t\t\t   Time: "<<timeStr;
    cout<<endl;
    cout << "\t\t\t+-----+-----+-----+-----+-----+" << endl;
    cout << "\t\t\t|  " <<blockOne << "  |  " << blockTwo << "  |  " << blockThree << "  |  " << blockFour << "  |  " << blockFive <<"  |"<< endl;
    cout << "\t\t\t+-----+-----+-----+-----+-----+" << endl;
    cout << "\t\t\t|  " <<blockSix << "  |  " << blockSeven << "  |  " << blockEight << "  |  " << blockNine << "  |  " << blockTen <<"  |"<< endl;
    cout << "\t\t\t+-----+-----+-----+-----+-----+" << endl;
    cout << "\t\t\t|  " <<blockEleven << "  |  " << blockTwelve << "  |  " << blockThirteen << "  |  " << blockFourteen << "  |  " << blockFifteen <<"  |"<< endl;
    cout << "\t\t\t+-----+-----+-----+-----+-----+" << endl;
    cout << "\t\t\t|  " <<blockSixteen << "  |  " << blockSeventeen << "  |  " << blockEighteen << "  |  " << blockNineteen << "  |  " << blockTwenty <<"  |"<< endl;
    cout << "\t\t\t+-----+-----+-----+-----+-----+" << endl;
    cout << "\t\t\t|  " <<blockTwentyOne << "  |  " << blockTwentyTwo << "  |  " << blockTwentyThree << "  |  " << blockTwentyFour << "  |  " << blockTwentyFive <<"  |"<< endl;
    cout << "\t\t\t+-----+-----+-----+-----+-----+" << endl;
}

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

void secondOption()
{
   cout<<"\n";
   cout<<"\t\t\t     ======================    "<<endl;
   cout<<"\t\t\t      &  &   &    &   &&&      "<<endl;
   cout<<"\t\t\t      &&&&    &  &    &  &     "<<endl;
   cout<<"\t\t\t      &  &     &&     &&&      "<<endl;
   cout<<"\t\t\t     ======================    "<<endl;
   cout<<"\n\n";
   cout<<"\t\tEnter Name for Player 1 : ";
   cin.ignore();
 	 cin.getline(firstPlayer,100);
   cout<<"\n\n";
 	 cout<< "\t\tEnter Name for Player 2 : ";
 	 cin.getline(secondPlayer,100);
   cout<<"\n\n";
   getch();
   clrscr();

   cout<<"\n";
   cout<<"\t\t\t     ======================    "<<endl;
   cout<<"\t\t\t      &  &   &    &   &&&      "<<endl;
   cout<<"\t\t\t      &&&&    &  &    &  &     "<<endl;
   cout<<"\t\t\t      &  &     &&     &&&      "<<endl;
   cout<<"\t\t\t     ======================    "<<endl;
   cout<<"\n\n";
   cout<<"\t\t\t"<<firstPlayer<<"  ==> [X] \n";       //to input the first_player name
   cout<<"\n\n";
   cout<<"\t\t\t"<<secondPlayer<<"  ==> [O] \n";      //to input the second_player name
   cout<<"\n\n";
   cout<<"\n\n";
   cout<<"\n\n";
}


/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

int checkWinComputer() // This function is to check whether the computer win or lose when their opponent is player
{
    if(blockOne == 'O' && blockSeven == 'O' && blockThirteen == 'O' && blockNineteen == 'O' && blockTwentyFive == 'O' && playerTurn == false) ////at first_option diagonal, a - s = y
        gameWin = 2; //This will make computer win.
    if(blockFive == 'O' && blockNine == 'O' && blockThirteen == 'O' && blockSeventeen == 'O' && blockTwentyOne == 'O' && playerTurn == false) ////at first_option diagonal, e - q = u
        gameWin = 2;
    if(blockOne == 'O' && blockTwo == 'O' && blockThree == 'O' && blockFour == 'O' && blockFive == 'O' && playerTurn == false) ////at first_option horizontal a - d = e
        gameWin = 2;
    if(blockSix == 'O' && blockSeven == 'O' && blockEight == 'O' && blockNine == 'O' && blockTen == 'O' && playerTurn == false) ////at first_option horizontal f - i = j
        gameWin = 2;
    if(blockEleven == 'O' && blockTwelve == 'O' && blockThirteen == 'O' && blockFourteen == 'O' && blockFifteen == 'O' && playerTurn == false) ////at first_option horizontal k - n = #
        gameWin = 2;
    if(blockSixteen == 'O' && blockSeventeen == 'O' && blockEighteen == 'O' && blockNineteen == 'O' && blockTwenty == 'O' && playerTurn == false) ////at first_option horizontal p - s = t
        gameWin = 2;
    if(blockTwentyOne == 'O' && blockTwentyTwo == 'O' && blockTwentyThree == 'O' && blockTwentyFour == 'O' && blockTwentyFive == 'O' && playerTurn == false) ////at first_option horizontal u - + = y
        gameWin = 2;
    if(blockOne == 'O' && blockSix == 'O' && blockEleven == 'O' && blockSixteen == 'O' && blockTwentyOne == 'O' && playerTurn == false) ////at first_option vertical a - p = u
        gameWin = 2;
    if(blockTwo == 'O' && blockSeven == 'O' && blockTwelve == 'O' && blockSeventeen == 'O' && blockTwentyTwo == 'O' && playerTurn == false) ////at first_option vertical b - q = v
        gameWin = 2;
    if(blockThree == 'O' && blockEight == 'O' && blockThirteen == 'O' && blockEighteen == 'O' && blockTwentyThree == 'O' && playerTurn == false) ////at first_option vertical c - r = w
        gameWin = 2;
    if(blockFour == 'O' && blockNine == 'O' && blockFourteen == 'O' && blockNineteen == 'O' && blockTwentyFour == 'O' && playerTurn == false) ////at first_option vertical d - s = +
        gameWin = 2;
    if(blockFive == 'O' && blockTen == 'O' && blockFifteen == 'O' && blockTwenty == 'O' && blockTwentyFive == 'O' && playerTurn == false) ////at first_option vertical e - t = y
        gameWin = 2;
    return 0;
}

int checkWinPlayer()   // This function is to check whether the user win or lose when their opponent is computer
{
    if(blockOne == 'X' && blockSeven == 'X' && blockThirteen == 'X' && blockNineteen == 'X' && blockTwentyFive == 'X' && playerTurn == true) ////at first_option diagonal, a - s = y
        gameWin = 1;
    if(blockFive == 'X' && blockNine == 'X' && blockThirteen == 'X' && blockSeventeen == 'X' && blockTwentyOne == 'X' && playerTurn == true) ////at first_option diagonal, e - q = u
        gameWin = 1;
    if(blockOne == 'X' && blockTwo == 'X' && blockThree == 'X' && blockFour == 'X' && blockFive == 'X' && playerTurn == true) ////at first_option horizontal a - d = e
        gameWin = 1;
    if(blockSix == 'X' && blockSeven == 'X' && blockEight == 'X' && blockNine == 'X' && blockTen == 'X' && playerTurn == true) ////at first_option horizontal f - i = j
        gameWin = 1;
    if(blockEleven == 'X' && blockTwelve == 'X' && blockThirteen == 'X' && blockFourteen == 'X' && blockFifteen == 'X' && playerTurn == true) ////at first_option horizontal k - n = #
        gameWin = 1;
    if(blockSixteen == 'X' && blockSeventeen == 'X' && blockEighteen == 'X' && blockNineteen == 'X' && blockTwenty == 'X' && playerTurn == true) ////at first_option horizontal p - s = t
        gameWin = 1;
    if(blockTwentyOne == 'X' && blockTwentyTwo == 'X' && blockTwentyThree == 'X' && blockTwentyFour == 'X' && blockTwentyFive == 'X' && playerTurn == true) ////at first_option horizontal u - + = y
        gameWin = 1;
    if(blockOne == 'X' && blockSix == 'X' && blockEleven == 'X' && blockSixteen == 'X' && blockTwentyOne == 'X' && playerTurn == true) ////at first_option vertical a - p = u
        gameWin = 1;
    if(blockTwo == 'X' && blockSeven == 'X' && blockTwelve == 'X' && blockSeventeen == 'X' && blockTwentyTwo == 'X' && playerTurn == true) ////at first_option vertical b - q = v
        gameWin = 1;
    if(blockThree == 'X' && blockEight == 'X' && blockThirteen == 'X' && blockEighteen == 'X' && blockTwentyThree == 'X' && playerTurn == true) ////at first_option vertical c - r = w
        gameWin = 1;
    if(blockFour == 'X' && blockNine == 'X' && blockFourteen == 'X' && blockNineteen == 'X' && blockTwentyFour == 'X' && playerTurn == true) ////at first_option vertical d - s = +
        gameWin = 1;
    if(blockFive == 'X' && blockTen == 'X' && blockFifteen == 'X' && blockTwenty == 'X' && blockTwentyFive == 'X' && playerTurn == true) ////at first_option vertical e - t = y
        gameWin = 1;
    return 0;
}

int computerAI() //work on computerAI part where the computer tries to win before countering.
{
    playerTurn == false;

    if(blockOne == 'O' && blockTwo == 'O' && blockThree == 'O' && blockFour == 'O' && playerTurn == false && blockFive == 'e') ////at first_option a - d = e win
    {
        blockFive = 'O';
        playerTurn = true;
    }

    if(blockSix == 'O' && blockSeven == 'O' && blockEight == 'O' && blockNine == 'O' && playerTurn == false && blockTen == 'j') ////at first_option f - i = j win
    {
        blockTen = 'O';
        playerTurn = true;
    }

    if(blockEleven == 'O' && blockTwelve == 'O' && blockThirteen == 'O' && blockFourteen == 'O' && playerTurn == false && blockFifteen == '#')////at first_option k - n = "#" win
    {
        blockFifteen = 'O';
        playerTurn = true;
    }

    if(blockSixteen == 'O' && blockSeventeen == 'O' && blockEighteen == 'O' && blockNineteen == 'O' && playerTurn == false && blockTwenty == 't')////at first_option p - s = t win
    {
        blockTwenty = 'O';
        playerTurn = true;
    }

    if(blockTwentyOne == 'O' && blockTwentyTwo == 'O' && blockTwentyThree == 'O' && blockTwentyFour == 'O' && playerTurn == false && blockTwentyFive == 'y') ////at first_option u - "-" = y win
    {
        blockTwentyFive = 'O';
        playerTurn = true;
    }

    if(blockOne == 'O' && blockSix == 'O' && blockEleven == 'O' && blockSixteen == 'O' && playerTurn == false && blockTwentyOne == 'u') ////at first_option a - p = u win
    {
        blockTwentyOne = 'O';
        playerTurn = true;
    }

    if(blockTwo == 'O' && blockSeven == 'O' && blockTwelve == 'O' && blockSeventeen == 'O' && playerTurn == false && blockTwentyTwo == 'v') ////at first_option b - q = v win
    {
        blockTwentyTwo = 'O';
        playerTurn = true;
    }

    if(blockThree == 'O' && blockEight == 'O' && blockThirteen == 'O' && blockEighteen == 'O' && playerTurn == false && blockTwentyThree == 'w')////at first_option c - r = w win
    {
        blockTwentyThree = 'O';
        playerTurn == true;
    }

    if(blockFour == 'O' && blockNine == 'O' && blockFourteen == 'O' && blockNineteen == 'O' && playerTurn == false && blockTwentyFour == '+') ////at first_option d - s = "-" win
    {
        blockTwentyFour = 'O';
        playerTurn == true;
    }

    if(blockFive == 'O' && blockTen == 'O' && blockFifteen == 'O' && blockTwenty == 'O' && playerTurn == false && blockTwentyFive == 'y') ////at first_option e - t = y win
    {
        blockTwentyFive = 'O';
        playerTurn == true;
    }

    if(blockOne == 'O' && blockSeven == 'O' && blockThirteen == 'O' && blockNineteen == 'O' && playerTurn == false && blockTwentyFive == 'y') ////at first_option e - q = u win
    {
        blockTwentyFive = 'O';
        playerTurn == true;
    }

    if(blockFive == 'O' && blockNine == 'O' && blockThirteen == 'O' && blockSeventeen == 'O' && playerTurn == false && blockTwentyOne == 'u') ////at first_option a - s = y win
    {
        blockTwentyOne = 'O';
        playerTurn == true;
    }

    if((playerChoice == 'e' || playerChoice == 'i' || playerChoice == 'm' || playerChoice == 'q' || playerChoice == 'u') && playerTurn == false)
    {
        if((blockFive == 'X' && blockNine == 'X' && blockThirteen == 'X' && blockSeventeen == 'X') && playerTurn == false && blockTwentyOne == 'u')////at first_option e - q = u diagonal
        {
            blockTwentyOne = 'O';
            playerTurn = true;
        }

        if((blockFive == 'X' && blockThirteen == 'X' && blockSeventeen == 'X' && blockTwentyOne == 'X') && playerTurn == false && blockNine == 'i') ////at first_option e - u = i diagonal
        {
            blockNine = 'O';
            playerTurn = true;
        }

        if((blockFive == 'X' && blockNine == 'X' && blockSeventeen == 'X' && blockTwentyOne == 'X') && playerTurn == false && blockThirteen == 'm') ////at first_option e - u = m diagonal
        {
            blockThirteen = 'O';
            playerTurn = true;
        }

        if((blockFive == 'X' && blockNine == 'X' && blockThirteen == 'X' && blockTwentyOne == 'X') && playerTurn == false && blockSeventeen == 'q') ////at first_option e - u = q diagonal
        {
            blockSeventeen = 'O';
            playerTurn = true;
        }

        if((blockNine == 'X' && blockThirteen == 'X' && blockSeventeen == 'X' && blockTwentyOne == 'X') && playerTurn == false && blockFive == 'e') ////at first_option u - i = e diagonal
        {
            blockFive = 'O';
            playerTurn = true;
        }
    }

    if((playerChoice == 'a' || playerChoice == 'g' || playerChoice == 'm' || playerChoice == 's' || playerChoice == 'y') && playerTurn == false)
    {
        if((blockOne == 'X' && blockSeven == 'X' && blockThirteen == 'X' && blockNineteen == 'X') && playerTurn == false && blockTwentyFive == 'y') ////at first_option a - s = y diagonal
        {
            blockTwentyFive = 'O';
            playerTurn = true;
        }

        if((blockOne == 'X' && blockThirteen == 'X' && blockNineteen == 'X' && blockTwentyFive == 'X') && playerTurn == false && blockSeven == 'g') ////at first_option a - y= g diagonal
        {
            blockSeven = 'O';
            playerTurn = true;
        }

        if((blockOne == 'X' && blockSeven == 'X' && blockNineteen == 'X' && blockTwentyFive == 'X') && playerTurn == false && blockThirteen == 'm') ////at first_option a - y = m diagonal
        {
            blockThirteen = 'O';
            playerTurn = true;
        }

        if((blockOne == 'X' && blockSeven == 'X' && blockThirteen == 'X' && blockTwentyFive == 'X') && playerTurn == false && blockNineteen == 's') ////at first_option a - y = s diagonal
        {
            blockNineteen = 'O';
            playerTurn = true;
        }

        if((blockSeven == 'X' && blockThirteen == 'X' && blockNineteen == 'X' && blockTwentyFive == 'X') && playerTurn == false && blockOne == 'a') ////at first_option y - g = a diagonal
        {
            blockOne = 'O';
            playerTurn = true;
        }
    }

    if((playerChoice == 'a' || playerChoice == 'b' || playerChoice == 'c' || playerChoice == 'd' || playerChoice == 'e') && playerTurn == false)
    {
        if((blockOne == 'X' && blockTwo == 'X' && blockThree == 'X' && blockFour == 'X') && playerTurn == false && blockFive == 'e') ////at first_option  a - d = e horizontal
        {
            blockFive = 'O';
            playerTurn = true;
        }

        if((blockOne == 'X' && blockTwo == 'X' && blockThree == 'X' && blockFive == 'X') && playerTurn == false && blockFour == 'd') ////at first_option 1 - 3 = 2 horizontal
        {
            blockFour = 'O';
            playerTurn = true;
        }

        if((blockOne == 'X' && blockTwo == 'X' && blockFive == 'X' && blockFour == 'X') && playerTurn == false && blockThree == 'c') ////at first_option 2 - 3 = 1 horizontal
        {
            blockThree = 'O';
            playerTurn = true;
        }

        if((blockOne == 'X' && blockFive == 'X' && blockThree == 'X' && blockFour == 'X') && playerTurn == false && blockTwo == 'b') ////at first_option 2 - 3 = 1 horizontal
        {
            blockTwo = 'O';
            playerTurn = true;
        }

        if((blockTwo == 'X' && blockThree == 'X' && blockFour == 'X' && blockFive == 'X') && playerTurn == false && blockOne == 'a') ////at first_option 2 - 3 = 1 horizontal
        {
            blockOne = 'O';
            playerTurn = true;
        }
    }

    if((playerChoice == 'f' || playerChoice == 'g' || playerChoice == 'h' || playerChoice == 'i' || playerChoice == 'j') && playerTurn == false)
    {
        if((blockSix == 'X' && blockSeven == 'X' && blockEight == 'X' && blockNine == 'X') && playerTurn == false && blockTen == 'j') ////at first_option 4 - 5 = 6 horizontal line 2
        {
            blockTen = 'O';
            playerTurn = true;
        }

        if((blockSix == 'X' && blockSeven == 'X' && blockEight == 'X' && blockTen == 'X') && playerTurn == false && blockNine == 'i') ////at first_option 4 - 6  = 5 horizontal line 2
        {
            blockNine = 'O';
            playerTurn = true;
        }

        if((blockSix == 'X' && blockSeven == 'X' && blockNine == 'X' && blockTen == 'X') && playerTurn == false && blockEight == 'h') ////at first_option 5 - 6 = 4 horizontal line 2
        {
            blockEight = 'O';
            playerTurn = true;
        }

        if((blockSix == 'X' && blockEight == 'X' && blockNine == 'X' && blockTen == 'X') && playerTurn == false && blockSeven == 'g') ////at first_option 2 - 3 = 1 horizontal
        {
            blockSeven = 'O';
            playerTurn = true;
        }

        if((blockSeven == 'X' && blockEight == 'X' && blockNine == 'X' && blockTen == 'X') && playerTurn == false && blockSix == 'f') ////at first_option 2 - 3 = 1 horizontal
        {
            blockSix = 'O';
            playerTurn = true;
        }
    }

    if((playerChoice == 'k' || playerChoice == 'l' || playerChoice == 'm' || playerChoice == 'n' || playerChoice == '#') && playerTurn == false)
    {
        if((blockEleven == 'X' && blockTwelve == 'X' && blockThirteen == 'X' && blockFourteen == 'X') && playerTurn == false && blockFifteen == '#') ////at first_option 7 - 8 = 9 horizontal line 3
        {
            blockFifteen = 'O';
            playerTurn = true;
        }

        if((blockEleven == 'X' && blockTwelve == 'X' && blockThirteen == 'X' && blockFifteen == 'X') && playerTurn == false && blockFourteen == 'n') ////at first_option 7 - 9 = 8 horizontal line 3
        {
            blockFourteen = 'O';
            playerTurn = true;
        }

        if((blockEleven == 'X' && blockTwelve == 'X' && blockFifteen == 'X' && blockFourteen == 'X') && playerTurn == false && blockThirteen == 'm') ////at first_option 8 - 9 = 7 horizontal line 3
        {
            blockThirteen = 'O';
            playerTurn = true;
        }

        if((blockEleven == 'X' && blockFifteen == 'X' && blockThirteen == 'X' && blockFourteen == 'X') && playerTurn == false && blockTwelve == 'l') ////at first_option 2 - 3 = 1 horizontal 3
        {
            blockTwelve = 'O';
            playerTurn = true;
        }

        if((blockFifteen == 'X' && blockTwelve == 'X' && blockThirteen == 'X' && blockFourteen == 'X') && playerTurn == false && blockEleven == 'k') ////at first_option 2 - 3 = 1 horizontal 3
        {
            blockEleven = 'O';
            playerTurn = true;
        }
    }

    if((playerChoice == 'p' || playerChoice == 'q' || playerChoice == 'r' || playerChoice == 's' || playerChoice == 't') && playerTurn == false)
    {
        if((blockSixteen == 'X' && blockSeventeen == 'X' && blockEighteen == 'X' && blockNineteen == 'X') && playerTurn == false && blockTwenty == 't') ////at first_option 7 - 8 = 9 horizontal line 4
        {
            blockTwenty = 'O';
            playerTurn = true;
        }

        if((blockSixteen == 'X' && blockSeventeen == 'X' && blockEighteen == 'X' && blockTwenty == 'X') && playerTurn == false && blockNineteen == 's') ////at first_option 7 - 9 = 8 horizontal line 4
        {
            blockNineteen = 'O';
            playerTurn = true;
        }

        if((blockSixteen == 'X' && blockSeventeen == 'X' && blockTwenty == 'X' && blockNineteen == 'X') && playerTurn == false && blockEighteen == 'r') ////at first_option 8 - 9 = 7 horizontal line 4
        {
            blockEighteen = 'O';
            playerTurn = true;
        }

        if((blockSixteen == 'X' && blockTwenty == 'X' && blockEighteen == 'X' && blockNineteen == 'X') && playerTurn == false && blockSeventeen == 'q') ////at first_option 2 - 3 = 1 horizontal 4
        {
            blockSeventeen = 'O';
            playerTurn = true;
        }

        if((blockTwenty == 'X' && blockSeventeen == 'X' && blockEighteen == 'X' && blockNineteen == 'X') && playerTurn == false && blockSixteen == 'p') ////at first_option 2 - 3 = 1 horizontal 4
        {
            blockSixteen = 'O';
            playerTurn = true;
        }
    }

    if((playerChoice == 'u' || playerChoice == 'v' || playerChoice == 'w' || playerChoice == '+' || playerChoice == 'y') && playerTurn == false)
    {
        if((blockTwentyOne == 'X' && blockTwentyTwo == 'X' && blockTwentyThree == 'X' && blockTwentyFour == 'X') && playerTurn == false && blockTwentyFive == 'y') ////at first_option 7 - 8 = 9 horizontal line 5
        {
            blockTwentyFive = 'O';
            playerTurn = true;
        }

        if((blockTwentyOne == 'X' && blockTwentyTwo == 'X' && blockTwentyThree == 'X' && blockTwentyFive == 'X') && playerTurn == false && blockTwentyFour == '+') ////at first_option 7 - 9 = 8 horizontal line 5
        {
            blockTwentyFour = 'O';
            playerTurn = true;
        }

        if((blockTwentyOne == 'X' && blockTwentyTwo == 'X' && blockTwentyFive == 'X' && blockTwentyFour == 'X') && playerTurn == false && blockTwentyThree == 'w') ////at first_option 8 - 9 = 7 horizontal line 5
        {
            blockTwentyThree = 'O';
            playerTurn = true;
        }

        if((blockTwentyOne == 'X' && blockTwentyFive == 'X' && blockTwentyThree == 'X' && blockTwentyFour == 'X') && playerTurn == false && blockTwentyTwo == 'v') ////at first_option 2 - 3 = 1 horizontal 5
        {
            blockTwentyTwo = 'O';
            playerTurn = true;
        }

        if((blockTwentyFive == 'X' && blockTwentyTwo == 'X' && blockTwentyThree == 'X' && blockTwentyFour == 'X') && playerTurn == false && blockTwentyOne == 'u') ////at first_option 2 - 3 = 1 horizontal 5
        {
            blockTwentyOne = 'O';
            playerTurn = true;
        }
    }

    if((playerChoice == 'a' || playerChoice == 'f' || playerChoice == 'k' || playerChoice == 'p' || playerChoice == 'u') && playerTurn == false)
    {
        if((blockOne == 'X' && blockSix == 'X' && blockEleven == 'X' && blockSixteen == 'X') && playerTurn == false && blockTwentyOne == 'u') ////at first_option 1 - 4 = 7 vertical row 1
        {
            blockTwentyOne = 'O';
            playerTurn = true;
        }

        if((blockOne == 'X' && blockSix == 'X' && blockEleven == 'X' && blockTwentyOne == 'X') && playerTurn == false && blockSixteen == 'p') ////at first_option 1 - 7 = 4 vertical row 1
        {
            blockSixteen = 'O';
            playerTurn = true;
        }

        if((blockOne == 'X' && blockSix == 'X' && blockTwentyOne == 'X' && blockSixteen == 'X') && playerTurn == false && blockEleven == 'k') ////at first_option 4 - 7 = 1 vertical row 1
        {
            blockEleven = 'O';
            playerTurn = true;
        }

        if((blockOne == 'X' && blockTwentyOne == 'X' && blockEleven == 'X' && blockSixteen == 'X') && playerTurn == false && blockSix == 'f') ////at first_option 4 - 7 = 1 vertical row 1
        {
            blockSix = 'O';
            playerTurn = true;
        }

        if((blockTwentyOne == 'X' && blockSix == 'X' && blockEleven == 'X' && blockSixteen == 'X') && playerTurn == false && blockOne == 'a') ////at first_option 4 - 7 = 1 vertical row 1
        {
            blockOne = 'O';
            playerTurn = true;
        }

    }

    if((playerChoice == 'b' || playerChoice == 'g' || playerChoice == 'i' || playerChoice == 'q' || playerChoice == 'v') && playerTurn == false)
    {
        if((blockTwo == 'X' && blockSeven == 'X' && blockTwelve == 'X' && blockSeventeen == 'X') && playerTurn == false && blockTwentyTwo == 'v') ////at first_option 2 - 5 = 8 vertical row 2
        {
            blockTwentyTwo = 'O';
            playerTurn = true;
        }

        if((blockTwo == 'X' && blockSeven == 'X' && blockTwelve == 'X' && blockTwentyTwo == 'X') && playerTurn == false && blockSeventeen == 'q') ////at first_option 2 - 8 = 5 vertical row 2
        {
            blockSeventeen = 'O';
            playerTurn = true;
        }

        if((blockTwo == 'X' && blockSeven == 'X' && blockTwentyTwo == 'X' && blockSeventeen == 'X') && playerTurn == false && blockTwelve == 'i') ////at first_option 5 - 8 = 2 vertical row 2
        {
            blockTwelve = 'O';
            playerTurn = true;
        }

        if((blockTwo == 'X' && blockTwentyTwo == 'X' && blockTwelve == 'X' && blockSeventeen == 'X') && playerTurn == false && blockSeven == 'g') ////at first_option 5 - 8 = 2 vertical row 2
        {
            blockSeven = 'O';
            playerTurn = true;
        }

        if((blockTwentyTwo == 'X' && blockSeven == 'X' && blockTwelve == 'X' && blockSeventeen == 'X') && playerTurn == false && blockTwo == 'b') ////at first_option 5 - 8 = 2 vertical row 2
        {
            blockTwo = 'O';
            playerTurn = true;
        }
    }

    if((playerChoice == 'c' || playerChoice == 'h' || playerChoice == 'm' || playerChoice == 'r' || playerChoice == 'w') && playerTurn == false)
    {
        if((blockThree == 'X' && blockEight == 'X' && blockThirteen == 'X' && blockEighteen == 'X') && playerTurn == false && blockTwentyThree == 'w') ////at first_option 2 - 5 = 8 vertical row 3
        {
            blockTwentyThree = 'O';
            playerTurn = true;
        }

        if((blockThree == 'X' && blockEight == 'X' && blockThirteen == 'X' && blockTwentyThree == 'X') && playerTurn == false && blockEighteen == 'r') ////at first_option 2 - 8 = 5 vertical row 3
        {
            blockEighteen = 'O';
            playerTurn = true;
        }

        if((blockThree == 'X' && blockEight == 'X' && blockTwentyThree == 'X' && blockEighteen == 'X') && playerTurn == false && blockThirteen == 'm') ////at first_option 5 - 8 = 2 vertical row 3
        {
            blockThirteen = 'O';
            playerTurn = true;
        }

        if((blockThree == 'X' && blockTwentyThree == 'X' && blockThirteen == 'X' && blockEighteen == 'X') && playerTurn == false && blockEight == 'h') ////at first_option 5 - 8 = 2 vertical row 3
        {
            blockEight = 'O';
            playerTurn = true;
        }

        if((blockTwentyThree == 'X' && blockEight == 'X' && blockThirteen == 'X' && blockEighteen == 'X') && playerTurn == false && blockThree == 'c') ////at first_option 5 - 8 = 2 vertical row 3
        {
            blockTwo = 'O';
            playerTurn = true;
        }
    }

    if((playerChoice == 'd' || playerChoice == 'i' || playerChoice == 'n' || playerChoice == 's' || playerChoice == '+') && playerTurn == false)
    {
        if((blockFour == 'X' && blockNine == 'X' && blockFourteen == 'X' && blockNineteen == 'X') && playerTurn == false && blockTwentyFour == '+') ////at first_option 2 - 5 = 8 vertical row 4
        {
            blockTwentyFour = 'O';
            playerTurn = true;
        }

        if((blockFour == 'X' && blockNine == 'X' && blockFourteen == 'X' && blockTwentyFour == 'X') && playerTurn == false && blockNineteen == 's') ////at first_option 2 - 8 = 5 vertical row 4
        {
            blockNineteen = 'O';
            playerTurn = true;
        }

        if((blockFour == 'X' && blockNine == 'X' && blockTwentyFour == 'X' && blockNineteen == 'X') && playerTurn == false && blockFourteen == 'n') ////at first_option 5 - 8 = 2 vertical row 4
        {
            blockFourteen = 'O';
            playerTurn = true;
        }

        if((blockFour == 'X' && blockTwentyFour == 'X' && blockFourteen == 'X' && blockNineteen == 'X') && playerTurn == false && blockNine == 'i') ////at first_option 5 - 8 = 2 vertical row 4
        {
            blockNine = 'O';
            playerTurn = true;
        }

        if((blockTwentyFour == 'X' && blockNine == 'X' && blockFourteen == 'X' && blockNineteen == 'X') && playerTurn == false && blockFour == 'd') ////at first_option 5 - 8 = 2 vertical row 4
        {
            blockFour = 'O';
            playerTurn = true;
        }
    }

    if((playerChoice == 'e' || playerChoice == 'j' || playerChoice == '#' || playerChoice == 't' || playerChoice == 'y') && playerTurn == false)
    {
        if((blockFive == 'X' && blockTen == 'X' && blockFifteen == 'X' && blockTwenty == 'X') && playerTurn == false && blockTwentyFive == 'y') ////at first_option 3 - 6 = 9 vertical row 5
        {
            blockTwentyFive = 'O';
            playerTurn = true;
        }

        if((blockFive == 'X' && blockTen == 'X' && blockFifteen == 'X' && blockTwentyFive == 'X') && playerTurn == false && blockTwenty == 't') ////at first_option 3 - 9 = 6 vertical row 5
        {
            blockTwenty = 'O';
            playerTurn = true;
        }

        if((blockFive == 'X' && blockTen == 'X' && blockTwentyFive == 'X' && blockTwenty == 'X') && playerTurn == false && blockFifteen == '#') ////at first_option 6 - 9 = 3 vertical row 5
        {
            blockFifteen = 'O';
            playerTurn = true;
        }

        if((blockFive == 'X' && blockTwentyFive == 'X' && blockFifteen == 'X' && blockTwenty == 'X') && playerTurn == false && blockTen == 'j') ////at first_option 6 - 9 = 3 vertical row 5
        {
            blockTen = 'O';
            playerTurn = true;
        }

        if((blockTwentyFive == 'X' && blockTen == 'X' && blockFifteen == 'X' && blockTwenty == 'X') && playerTurn == false && blockFive == 'e') ////at first_option 6 - 9 = 3 vertical row 5
        {
            blockFive = 'O';
            playerTurn = true;
        }
    }
    else
    {
        do
        {

            if(blockOne == 'a' && playerTurn == false)
            {
                playerTurn = true;
                blockOne = 'O';
            }
            if(blockTwo == 'b' && playerTurn == false)
            {
                playerTurn = true;
                blockTwo = 'O';
            }
            if(blockThree == 'c' && playerTurn == false)
            {
                playerTurn = true;
                blockThree = 'O';
            }
            if(blockFour == 'd' && playerTurn == false)
            {
                playerTurn = true;
                blockFour = 'O';
            }
            if(blockFive == 'e' && playerTurn == false)
            {
                playerTurn = true;
                blockFive = 'O';
            }
            if(blockSix == 'f' && playerTurn == false)
            {
                playerTurn = true;
                blockSix = 'O';
            }
            if(blockSeven == 'g' && playerTurn == false)
            {
                playerTurn = true;
                blockSeven = 'O';
            }
            if(blockEight == 'h' && playerTurn == false)
            {
                playerTurn = true;
                blockEight = 'O';
            }
            if(blockNine == 'i' && playerTurn == false)
            {
                playerTurn = true;
                blockNine = 'O';
            }

            if(blockTen == 'j' && playerTurn == false)
            {
                playerTurn = true;
                blockNine = 'O';
            }

            if(blockEleven == 'k' && playerTurn == false)
            {
                playerTurn = true;
                blockEleven = 'O';
            }

            if(blockTwelve == 'l' && playerTurn == false)
            {
                playerTurn = true;
                blockTwelve = 'O';
            }

            if(blockThirteen == 'm' && playerTurn == false)
            {
                playerTurn = true;
                blockThirteen = 'O';
            }

            if(blockFourteen == 'n' && playerTurn == false)
            {
                playerTurn = true;
                blockFourteen = 'O';
            }

            if(blockFifteen == '#' && playerTurn == false)
            {
                playerTurn = true;
                blockFifteen = 'O';
            }

            if(blockSixteen == 'p' && playerTurn == false)
            {
                playerTurn = true;
                blockSixteen = 'O';
            }

            if(blockSeventeen == 'q' && playerTurn == false)
            {
                playerTurn = true;
                blockSeventeen = 'O';
            }

            if(blockEighteen == 'r' && playerTurn == false)
            {
                playerTurn = true;
                blockEighteen = 'O';
            }

            if(blockNineteen == 's' && playerTurn == false)
            {
                playerTurn = true;
                blockNineteen = 'O';
            }

            if(blockTwenty == 't' && playerTurn == false)
            {
                playerTurn = true;
                blockTwenty = 'O';
            }

            if(blockTwentyOne == 'u' && playerTurn == false)
            {
                playerTurn = true;
                blockTwentyOne = 'O';
            }

            if(blockTwentyTwo == 'v' && playerTurn == false)
            {
                playerTurn = true;
                blockTwentyTwo = 'O';
            }

            if(blockTwentyThree == 'w' && playerTurn == false)
            {
                playerTurn = true;
                blockTwentyThree = 'O';
            }

            if(blockTwentyFour == '+' && playerTurn == false)
            {
                playerTurn = true;
                blockTwentyFour = 'O';
            }

            if(blockTwentyFive == 'y' && playerTurn == false)
            {
                playerTurn = true;
                blockTwentyFive = 'O';
            }

        }
        while(playerTurn == false);
    }
    return 0;
}

int checkPlayerInput()     // This function for the user input and display what is the input from the user
{
    if(playerChoice == 'a' && blockOne == 'a')
        blockOne = 'X';
    if(playerChoice == 'b' && blockTwo == 'b')
        blockTwo = 'X';
    if(playerChoice == 'c' && blockThree == 'c')
        blockThree = 'X';
    if(playerChoice == 'd' && blockFour == 'd')
        blockFour = 'X';
    if(playerChoice == 'e' && blockFive == 'e')
        blockFive = 'X';
    if(playerChoice == 'f' && blockSix == 'f')
        blockSix = 'X';
    if(playerChoice == 'g' && blockSeven == 'g')
        blockSeven = 'X';
    if(playerChoice == 'h' && blockEight == 'h')
        blockEight = 'X';
    if(playerChoice == 'i' && blockNine == 'i')
        blockNine = 'X';
    if(playerChoice == 'j' && blockTen == 'j')
        blockTen = 'X';
    if(playerChoice == 'k' && blockEleven == 'k')
        blockEleven = 'X';
    if(playerChoice == 'l' && blockTwelve == 'l')
        blockTwelve = 'X';
    if(playerChoice == 'm' && blockThirteen == 'm')
        blockThirteen = 'X';
    if(playerChoice == 'n' && blockFourteen == 'n')
        blockFourteen = 'X';
    if(playerChoice == '#' && blockFifteen == '#')
        blockFifteen = 'X';
    if(playerChoice == 'p' && blockSixteen == 'p')
        blockSixteen = 'X';
    if(playerChoice == 'q' && blockSeventeen == 'q')
        blockSeventeen = 'X';
    if(playerChoice == 'r' && blockEighteen == 'r')
        blockEighteen = 'X';
    if(playerChoice == 's' && blockNineteen == 's')
        blockNineteen = 'X';
    if(playerChoice == 't' && blockTwenty == 't')
        blockTwenty = 'X';
    if(playerChoice == 'u' && blockTwentyOne == 'u')
        blockTwentyOne = 'X';
    if(playerChoice == 'v' && blockTwentyTwo == 'v')
        blockTwentyTwo = 'X';
    if(playerChoice == 'w' && blockTwentyThree == 'w')
        blockTwentyThree = 'X';
    if(playerChoice == '+' && blockTwentyFour == '+')
        blockTwentyFour = 'X';
    if(playerChoice == 'y' && blockTwentyFive == 'y')
        blockTwentyFive = 'X';

    return 0;
}

int checkComputerInput()   //This function is for the computer input and display what is the input from the computer
{
    if(computerPick == 'a' && blockOne == 'a')
        blockOne = 'O';
    if(computerPick == 'b' && blockTwo == 'b')
        blockTwo = 'O';
    if(computerPick == 'c' && blockThree == 'c')
        blockThree = 'O';
    if(computerPick == 'd' && blockFour == 'd')
        blockFour = 'O';
    if(computerPick == 'e' && blockFive == 'e')
        blockFive = 'O';
    if(computerPick == 'f' && blockSix == 'f')
        blockSix = 'O';
    if(computerPick == 'g' && blockSeven == 'g')
        blockSeven = 'O';
    if(computerPick == 'h' && blockEight == 'h')
        blockEight = 'O';
    if(computerPick == 'i' && blockNine == 'i')
        blockNine = 'O';
    if(computerPick == 'j' && blockTen == 'j')
        blockTen = 'O';
    if(computerPick == 'k' && blockEleven == 'k')
        blockEleven = 'O';
    if(computerPick == 'l' && blockTwelve == 'l')
        blockTwelve = 'O';
    if(computerPick == 'm' && blockThirteen == 'm')
        blockThirteen = 'O';
    if(computerPick == 'n' && blockFourteen == 'n')
        blockFourteen = 'O';
    if(computerPick == '#' && blockFifteen == '#')
        blockFifteen = 'O';
    if(computerPick == 'p' && blockSixteen == 'p')
        blockSixteen = 'O';
    if(computerPick == 'q' && blockSeventeen == 'q')
        blockSeventeen = 'O';
    if(computerPick == 'r' && blockEighteen == 'r')
        blockEighteen = 'O';
    if(computerPick == 's' && blockNineteen == 's')
        blockNineteen = 'O';
    if(computerPick == 't' && blockTwenty == 't')
        blockTwenty = 'O';
    if(computerPick == 'u' && blockTwentyOne == 'u')
        blockTwentyOne = 'O';
    if(computerPick == 'v' && blockTwentyTwo == 'v')
        blockTwentyTwo = 'O';
    if(computerPick == 'w' && blockTwentyThree == 'w')
        blockTwentyThree = 'O';
    if(computerPick == '+' && blockTwentyFour == '+')
        blockTwentyFour = 'O';
    if(computerPick == 'y' && blockTwentyFive == 'y')
        blockTwentyFive = 'O';

    return 0;
}

int checkTie()  // This function to determine for the user and computer whether they tie or not
{
    if(blockOne != 'a' && blockTwo != 'b' && blockThree != 'c' && blockFour != 'd' && blockFive != 'e' && blockSix != 'f' && blockSeven != 'g' && blockEight != 'h' &&
    	 blockNine != 'i' && blockTen != 'j' && blockEleven != 'k' && blockTwelve != 'l' && blockThirteen != 'm' && blockFourteen != 'n' && blockFifteen != '#' &&
       blockSixteen != 'p' && blockSeventeen != 'q' && blockEighteen != 'r' && blockNineteen != 's' && blockTwenty != 't' && blockTwentyOne != 'u' && blockTwentyTwo != 'v' &&
       blockTwentyThree != 'w' && blockTwentyFour != '+' && blockTwentyFive != 'y')
    {
        cout << "It's a tie!" << endl;
        gameWin = 0;
    }
   return 0;
}


main()    // This the main program of the whole coding
{
	 char option;

   loading();
   sleep(5);
   clrscr();
   hvd();

   getch();
   clrscr();
   cout<<"\n";
   cout<<"\t\t\t     ====================== "<<endl;
   cout<<"\t\t\t      &  &   &    &   &&&  "<<endl;
   cout<<"\t\t\t      &&&&    &  &    &  & "<<endl;
   cout<<"\t\t\t      &  &     &&     &&&  "<<endl;
   cout<<"\t\t\t     ====================== "<<endl;


 	cout<<"\n\n\n";
 	cout<<"\t\t\t   [A/a] ->    Single Player \n\n";
 	cout<<"\t\t\t   [B/b] ->    Multiplayer \n\n";
 	cout<<"\n\n";
 	cout<<"\t\t Enter Option: ";
 	cin>>option;

 if(option=='A'||option=='a')
 {
    srand(time(0));
    int playAgain;
    int playerScore = 0;
    int computerScore = 0;
    int ties = 0;

    do
    {
        clrscr();
        turnFirst = rand()%(2 - 1 + 1)+1;//generates starting person.
        computerRandomPick = rand()% (25 - 1 + 1)+1;//computer first pick - random
        gameWin = 3;

        blockOne = 'a';
        blockTwo = 'b';
        blockThree = 'c';
        blockFour = 'd';
		  blockFive = 'e';
        blockSix = 'f';
        blockSeven = 'g';
        blockEight = 'h';
        blockNine = 'i';
        blockTen = 'j';
        blockEleven = 'k';
        blockTwelve = 'l';
        blockThirteen = 'm';
        blockFourteen = 'n';
        blockFifteen = '#';
        blockSixteen = 'p';
        blockSeventeen = 'q';
        blockEighteen = 'r';
        blockNineteen = 's';
        blockTwenty = 't';
        blockTwentyOne = 'u';
        blockTwentyTwo = 'v';
        blockTwentyThree = 'w';
        blockTwentyFour = '+';
        blockTwentyFive = 'y';

        //BEGIN OF PROGRAM
         cout<<"\n";
   		cout<<"\t\t\t     ======================    "<<endl;
   		cout<<"\t\t\t      &  &   &    &   &&&      "<<endl;
   		cout<<"\t\t\t      &&&&    &  &    &  &     "<<endl;
   		cout<<"\t\t\t      &  &     &&     &&&      "<<endl;
   		cout<<"\t\t\t     ======================    "<<endl;
         cout<<"\n\n";
         cout<<"\t\t\t         -CURRENT SCORE-       ";
         cout<<"\n\n";
        	cout <<"\t\t[Player] ->  " << playerScore << "    [Computer] ->  "<< computerScore << "    [Ties] ->  " << ties << endl;
        	getch();
        	clrscr();


        if(turnFirst == 1)//player first
        {


            gameBoard();//Gameboard for tic tac toe
            while (!(cin >> playerChoice)) //error traps letters and words
            {
                cout << endl;
                cout << "Numbers only." << endl;
                cin.clear();
                cin.ignore(10000,'\n');
            }
            checkPlayerInput();
            clrscr();
            gameBoard();
            playerTurn = false; //switches to computer
        }

        if(turnFirst == 2)//Computer first
        {
            computerRandomPick;
            computerPick = computerRandomPick;
            checkComputerInput();

            playerTurn = true;
            gameBoard();
        }


        do
        {
            if(playerTurn == true) //player loop
            {
            	cout << "Please choose the alphabet/symbol to place 'X': "<<endl<<endl;
                while (!(cin >> playerChoice)) //error traps on numbers
                {
                    cout << endl;
                    cout << "Characters only." << endl;
                    cin.clear();
                    cin.ignore(100,'\n');
                }
                checkPlayerInput();
                checkWinPlayer();
                checkTie();
                playerTurn = false;
            }

            if(playerTurn == false) //computer loop
            {
                computerAI();
                clrscr();
                gameBoard();
                checkWinComputer();
                checkTie();
                playerTurn = true;
            }

        }
        while(gameWin > 2);

        if(gameWin == 0)
        {
            cout<<"\n\n";
            cout << "The game is a Tie!" << endl;
            ++ties;
        }


        if(gameWin == 1)
        {
            cout<<"\n\n";
            cout << "The player wins!" << endl;
            ++playerScore;
        }

        if(gameWin == 2)
        {
        		cout<<"\n\n";
            cout << "The computer wins!" << endl;
            ++computerScore;
        }


        cout <<"[Player] ->  " << playerScore << "    [Computer] ->  "<< computerScore << "    [Ties] ->  " << ties << endl;

        cout<<"Do you want to play again ??"<<endl;

        cout<<"[1] -> YES    [2] -> NO ";

        while (!(cin >> playAgain)) //error traps on numbers
        {
            cout << endl;
            cout<<"[1] -> YES    [2] -> NO ";
            cin.clear();
            cin.ignore(100,'\n');
        }


    }
    while(playAgain == 1);
    clrscr();
    display_ending();
  }
  else if(option=='B'||option=='b')
  {
      clrscr();
   	  secondOption();
   	  cout<<"\t\tPress ENTER to Start The Game....";
   	  turn = 'X';
   	  cout<<"\n\n";
   	  getch();
   	  clrscr();

   	while (!gameover())
   	{
       	display_board(board);
       	player_turn();
       	clrscr();
       	gameover();
   	}

   	if (turn == 'O' && !draw)
   	{
      	display_board(board);
       	cout<<endl<<endl<<" "<<firstPlayer<<"[X] Wins! Game Over!\n";

       	getch();
       	clrscr();
       	display_ending();
   	}

   	else if (turn == 'X' && !draw)
   	{
      	display_board(board);
      	cout<<endl<<endl<<" "<<secondPlayer<<"[O] Wins!     Game Over!\n";

      	getch();
      	clrscr();
      	display_ending();
   	}

   	else
   	{
      	display_board(board);
      	cout<<endl<<endl<<"It's a draw!    Game Over!\n";

      	getch();
      	clrscr();
      	display_ending();
   	}

   }
 	getch();
}

void player_turn()                                         //This function is to determine for the player turn
{
    char choice;
    int row = 0, column = 0;
    if (turn == 'X')
    {
      cout<<"\n\n";
    	cout<<" "<<firstPlayer<<" turn [X]: ";
    }

    else if (turn == 'O')
    {
    	cout<<"\n\n";
    	cout<<" "<<secondPlayer<<" turn [O]: ";
    }

    cin>>choice;

    switch (choice)
    {
    	  case 'a':
        		   row = 0; column = 0;
               break;

        case 'b':
					row = 0; column = 1;
				   break;

        case 'c':
					row = 0; column = 2;
               break;

        case 'd':
               row = 0; column = 3;
               break;

        case 'e':
        			row = 0; column = 4;
               break;

        case 'f':
        			row = 1; column = 0;
               break;

        case 'g':
        			row = 1; column = 1;
 					break;

        case 'h':
         		row = 1; column = 2;
            	break;

        case 'i':
        		  	row = 1; column = 3;
 					break;

        case 'j':
        		  	row = 1; column = 4;
 					break;

        case 'k':
        		  	row = 2; column = 0;
 					break;

        case 'l':
        		  	row = 2; column = 1;
 					break;

        case 'm':
        		  	row = 2; column = 2;
 					break;

        case 'n':
        		  	row = 2; column = 3;
 					break;

        case '=':
        		  	row = 2; column = 4;
 					break;

        case 'p':
        		  	row = 3; column = 0;
 					break;

        case 'q':
        		  	row = 3; column = 1;
 					break;

        case 'r':
        		  	row = 3; column = 2;
 					break;

        case 's':
        		  	row = 3; column = 3;
 					break;

        case 't':
        		  	row = 3; column = 4;
 					break;

        case 'u':
        		  	row = 4; column = 0;
 					break;

        case 'v':
        		  	row = 4; column = 1;
 					break;

        case 'w':
        		  	row = 4; column = 2;
 					break;

        case '#':
        		  	row = 4; column = 3;
 					break;

        case 'y':
        		  	row = 4; column = 4;
 					break;
        default:
            cout<<"You didn't enter a correct number! Try again\n\a\a\a\a";
            player_turn();
    }

    if (turn == 'X' && board[row][column] != 'X' && board[row][column] != 'O')

    {
        board[row][column] = 'X';
        turn = 'O';
	 }

    else if (turn == 'O' && board[row][column] != 'X' && board[row][column] != 'O')
    {
        board[row][column] = 'O';
        turn = 'X';
    }

    else
    {
        cout<<"\a\a\aThe cell you chose is used! Try again\n";
        player_turn();
    }
}


bool gameover()
{
    for (int i = 0; i < 5; i++)//Check for a win
	 {
    	if ((board[i][0] == board[i][1] && board[i][1] == board[i][2] && board[i][2] == board[i][3] && board[i][3] == board[i][4])||
          (board[0][i] == board[1][i] && board[1][i] == board[2][i] && board[2][i] == board[3][i] && board[3][i] == board[4][i])||
          (board[0][0] == board[1][1] && board[1][1] == board[2][2] && board[2][2] == board[3][3] && board[3][3] == board[4][4])||
          (board[0][4] == board[1][3] && board[1][3] == board[2][2] && board[2][2] == board[3][1] && board[3][1] == board[4][0]))
      {
  	      return true;
      }
    }


    for (int i = 0; i < 5; i++)//Check for draw
    {
    	for (int j = 0; j < 5; j++)
      {
      	if (board[i][j] != 'X' && board[i][j] != 'O')
         {
         	return false;
         }
      }
    }

    draw = true;
    return 0;
}
```
