```c++
#include <iostream>
using namespace std;

int main() {
    
    int timeof4 = 0;
    int vet[10]; // --> Note: Vector created.
    srand(time(0)); // --> Note: srand() = Seed Random. Get the time from the clock pulse as a seed.
    
    for(int i = 0; i < 10; i++){ // --> Note: Filling the vector "vet" with random numbers
        vet[i] = rand() % 10;
    }
    
    cout << "Vector value's \n"; // --> Note: Showing the value of the vector "vet".
    
    for (int i = 0; i < 10; i++){
        cout << vet[i] << ", ";
        if (vet[i] == 4){
            timeof4++;
        }
    }
    
    cout << "\n";
    
    for (int i = 9; i >= 0; i--){ // --> Note: Showing the value of the vector "vet" in reverse.
        cout << vet[i] << ", ";
    }
    
    cout << "\n " << timeof4;
    
    return 0;
}
```
### Filing a vector with random, not repeatable numbers.
```c++
#include <iostream>
using namespace std;

int main() {

    int N = 50, vet[N], n = 0;
    bool check;
    
    srand(time(0));
    
    for (int i = 0; i < N; i++){
        check = true;
        while (check){
            n = rand() % N;
            check = false;
            for (int j = 0; j < i; j++)
                if (vet[j] == n){
                    check = true;
                }
        }
        vet[i] = n;
        cout << vet[i] << " ";
    }
    return 0;
}
```
