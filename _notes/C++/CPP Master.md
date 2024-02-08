

[[string cpp 1]]
[[transform 1]]
[[npos 1]]
[[cpp_replace() 1]]

stoi ( to int)
[[setprecision() 1]]
abs

# 배열
[[cpp vector]]
[[cpp map]]

```cpp
#include <iostream>
#include <vector>
#include <random>
#include <ctime>

using namespace std;

int main() {
    srand(static_cast<unsigned int>(time(nullptr))); // Seed the random number generator

    int simulations = 10000;
    int successfulOutcomes = 0;

    for (int sim = 0; sim < simulations; ++sim) {
        vector<bool> seats(100, false); // Corrected to 100 seats

        // First passenger sits in a random seat
        seats[rand() % 100] = true;

        for (int i = 1; i < 99; ++i) { // Correct loop to start from 1 to 98
            if (!seats[i]) { // If their seat is free
                seats[i] = true; // They sit in it
            } else { // Otherwise, pick a random free seat
                int freeSeat;
                do {
                    freeSeat = rand() % 100;
                } while (seats[freeSeat]); // Ensure the loop continues until a free seat is found
                seats[freeSeat] = true;
            }
        }

        // Check if the last passenger's seat is free
        if (!seats[99]) successfulOutcomes++;
    }

    // Calculate and print the probability
    double probability = static_cast<double>(successfulOutcomes) / simulations;
    cout << "Probability of the last passenger getting their own seat: " << probability << endl;

    return 0;
}

```


static_cast
**static_cast<바꾸려고 하는 타입>(대상);  
static_cast<new_type>(expression)**

특징 (논리적으로 변환 가능한 타입을 변환한다)



```cpp
#include <iostream>
#include <vector>
#include <ctime>
#include <string>

using namespace std;

int main() {
   
    int N, M;

    cin >> N;
    //일단 특정숫자를 먼저 구해야함

    for (int i = 1; i < N; i++) {
       int sum = i;
       int temp = i;
        while (temp)
        {
            sum += temp % 10;
            temp /= 10;
        }
        if (sum == N) {
            cout << temp << endl;
            return 0;
        }
    }

    cout << "0" << endl; // If no constructor is found, print 0.
    return 0;
     
}

```

# 정렬
[[cpp sort]]

