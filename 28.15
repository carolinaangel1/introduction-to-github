//carolina angel 
// 
#include <iostream>
#include "PlaylistNode.h"

using namespace std;

void PrintMenu(const string playlistTitle) {
   // Step 3: Implement the PrintMenu() function.
   cout << endl;
   //playlist title 
   cout << playlistTitle << " PLAYLIST MENU" << endl;
   
   cout << "a - Add song" << endl;
   cout << "d - Remove song" << endl;
   cout << "c - Change position of song" << endl;
   cout << "s - Output songs by specific artist" << endl;
   cout << "t - Output total time of playlist (in seconds)" << endl;
   cout << "o - Output full playlist" << endl;
   cout << "q - Quit" << endl;
   cout << endl;
   
}

PlaylistNode* ExecuteMenu(char option, string playlistTitle, PlaylistNode* headNode) {
   // step 5 imlementing quit 
   if(option == 'q'){
       return headNode;
   }
   // step 6 output full playlist 
   // If the list is empty, output: Playlist is empty
   else if(option == 'o'){
      //empty
      if(headNode == nullptr){
           cout << playlistTitle << " - OUTPUT FULL PLAYLIST" << endl;
           cout << "Playlist is empty" << endl;
           return headNode;
      }
   
   // non empty list 
      PlaylistNode* currentPointer = headNode;
      int songCount = 1;
      cout << playlistTitle << " - OUTPUT FULL PLAYLIST" << endl;
      while(currentPointer != nullptr){
           cout << songCount <<  "." << endl;
           currentPointer->PrintPlaylistNode();
           currentPointer = currentPointer->GetNext();
           if(currentPointer != nullptr){
               cout << endl;
           }
         songCount++;
      }
   }
        
   // step 7 Implement the "Add song" menu option in ExecuteMenu()
   else if(option == 'a'){
      string id;
      string name;
      string artistName;
      int songLen;
      cout << "ADD SONG" << endl;
      cout << "Enter song's unique ID:" << endl;
      getline(cin, id);
      cout << "Enter song's name:" << endl;
      getline(cin, name);
      cout << "Enter artist's name:" << endl;
      getline(cin, artistName);
      cout << "Enter song's length (in seconds):" << endl;
      cin >> songLen;
      
      PlaylistNode* newSong = new PlaylistNode(id, name, artistName, songLen);
      if(headNode == nullptr){
         headNode = newSong;
         return headNode;
      }
      PlaylistNode* currNode = headNode;
       
      while(currNode->GetNext() != nullptr){
           currNode = currNode->GetNext();
      }
      //new additions added to the end of list 
      currNode->InsertAfter(newSong);
      return headNode;

   }
   //step 8 "remove song" option 
   else if(option == 'd'){

      string ID;
      cout << endl;
      cout << "REMOVE SONG" << endl;
      // promt the user for the id of the song to be removed 
      cout << "Enter song's unique ID:" << endl;
      cin >> ID;
   
      int count = 0;
   
      PlaylistNode* currSong = headNode;
       
      PlaylistNode* lastSong = nullptr;
   
      while(currSong->GetID() != ID){
         lastSong = currSong;
         currSong = currSong->GetNext();
         count++;
      }
      if(count == 0){
         PlaylistNode* newHead = headNode->GetNext();
         cout << "\"" << headNode->GetSongName() << "\" removed." << endl;
         delete headNode;
         return newHead;
      }
      lastSong->SetNext(currSong->GetNext());
      cout << "\"" << currSong->GetSongName() << "\" removed." << endl;
      delete currSong;
      return headNode;

   }
   // step 9 "Change position of song" menu option in ExecuteMenu
   else if(option == 'c'){
   // ignore this step 
   }
   // Step 10: Implement the "Output songs by specific artist" 
   else if (option == 's'){
      cout << "OUTPUT SONGS BY SPECIFIC ARTIST" << endl;
      // prompt the user for the artist name 
      cout << "Enter artist's name:" << endl;
    
      string artistToSearch;
      getline(cin, artistToSearch);

      PlaylistNode* currentPointer = headNode;
      int songCount = 1;
    
      while (currentPointer != nullptr) {
         if (currentPointer->GetArtistName() == artistToSearch) {
            cout << endl;
            cout << songCount << "." << endl;
            currentPointer->PrintPlaylistNode();
         }
         currentPointer = currentPointer->GetNext();
         songCount++;
      }
   
      return headNode;
   }
   
   //Step 11: Implement the "Output total time of playlist"
   else if (option == 't'){
      cout << "OUTPUT TOTAL TIME OF PLAYLIST (IN SECONDS)" << endl;
      int totalTime = 0;
      PlaylistNode* currentPointer = headNode;
      while (currentPointer != nullptr) {
         totalTime += currentPointer->GetSongLength();
         currentPointer = currentPointer->GetNext();
      }
      cout << "Total time: " << totalTime << " seconds" << endl;

      return headNode;
      
   }
}
        

int main() {
   string playlistTitle;
   char choice;
   PlaylistNode* head = nullptr;

// step 2 prompt the user for the title of the playlist.
   cout << "Enter playlist's title:" << endl;
   getline(cin, playlistTitle);

   PrintMenu(playlistTitle);

// step 5 
   cout << "Choose an option:" << endl;
   cin >> choice;
// the while loop for the choice    
   while(choice != 'q'){
      if(choice == 'a' || choice == 'd' || choice == 'c' || choice == 's' || choice == 't' || choice == 'o'){
         head = ExecuteMenu(choice, playlistTitle, head);
         PrintMenu(playlistTitle);
         cout << "Choose an option:" << endl;
         cin >> choice;
         cin.ignore();
           
       }
       else{
         cout << "Choose an option:" << endl;
         cin >> choice;
         cin.ignore();
       }
   }
   return 0;
   
}

