#include <iostream>
#include <string>
#include <vector>
using namespace std;

vector<int> listDeclaration(int listLen) {
  vector<int> numbers;
  for (int i = 0; i<listLen;i++) {
    int num;
    cout << ": ";
    cin >> num;
    numbers.push_back(num);
  }
  return numbers;
}


int numOfMoves(vector<int> numbers,int listLen) {
  int moves = 0;
  int amount;
  for (int i = 0;i < listLen-1;i++) {
    int &n1 = numbers[i];
    int &n2 = numbers[i+1];
    amount = 0;
    
    if (n1 <= n2) {
      continue;
    }
    else {
      amount = n1 - n2;
      moves += amount;
      n2 = n1;
      
    }
  }
  return moves;
}

int main() {
  int listLen;
  cout << "len: ";
  cin >> listLen;
  vector<int> numbers = listDeclaration(listLen);
  
  cout << numOfMoves(numbers,listLen);
  return 0;
}
