# Sorter
// I test a few sorting algorithms with this program. I am considering creating a code for the quicksort.
#include <iostream>
#include <string>
#include <cstdlib>
#include <unistd.h>
#include <math.h>
using namespace std;

int main(int argc, char *argv[]){
        void bubble(int[], int);
        void bucket(int[], int);
        void heap(int[], int);
        if (argc == 3){
                int b = 0;
                int numNums = atoi(argv[2]);
                int testRes[numNums];
                for (int i = 0; i < numNums; i++){
                        testRes[i] = rand() % 999999;
                }
                string algorithm = argv[1];
                if (algorithm == "bubble" && a == 1){
                        b = 1;
                        bubble(testRes, numNums);
                }
                if (algorithm == "bucket" && a == 1){
                        b = 1;
                        bucket(testRes, numNums);
                }
                if (algorithm == "heap" && a == 1){
                        b = 1;
                        heap(testRes, numNums);
                }
                if (b == 0){
                        cout << "Invalid input. Go away." << endl;
                }
        }
        else {
                cout << "Improper number of arguments. Go away." << endl;
        }
}

void bubble(int* ints, int x){
        void sorted(int*, int);
        int temp;
        while (x != 0){
                for (int i = 0; i < x - 1; i++){
                        if(ints[i] > ints[i + 1]){
                                temp = ints[i];
                                ints[i] = ints[i + 1];
                                ints[i + 1] = temp;
                        }
                }
                x--;
        }
        sorted(ints, x);
}

void bucket(int* ints, int numInts){
        void sorted(int*, int);
        int numCount[1000000];
        int y;
        for (int i = 0; i < numInts; i++){
                numCount[ints[i]]++;
        }
        for (int i = 0; i < numInts; i++){
                while (numCount[y] == 0){
                        y++;
                }
                ints[i] = y;
                numCount[y]--;
        }
        sorted(ints, numInts);
}

void heap(int* ints, int numInts){
        int temp;
        void sorted(int*, int);
        void makeHeap(int*, int, int);
        void heapifyDown(int*, int);
        makeHeap(ints, 0, numInts);
        for (int i = numInts - 1; i > -1; i--){
                heapifyDown(ints, i);
                temp = ints[0];
                ints[0] = ints[i];
                ints[i] = temp;
        }
        sorted(ints, numInts);
}

void makeHeap(int* i, int s, int n){
        int temp;
        int r;
        int k;
        for (int j = n - 1; j > -1; j--){
                r = j;
                k = j;
                while (r != 0){
                        r = (r - 1)/2;
                        if (i[r] < i[k]){
                                k = r;
                        }
                }
                temp = i[k];
                i[k] = i[j];
                i[j] = temp;
        }
}

void heapifyDown(int* i, int n){
        int temp;
        int b;
        int s = 0;
        while (2*s + 1 <= n){
                b = 0;
                if (2*s + 2 <= n){
                        if (i[s] < i[2*s + 1] && i[2*s + 1] >= i[2*s + 2]){
                                b = 1;
                        }
                        if (i[s] < i[2*s + 2] && i[2*s + 2] >= i[2*s + 1]){
                                b = 2;
                        }
                }
                else if (2*s + 2 > n && i[s] < i[2*s + 1]){
                                b = 1;
                }
                if (b != 0){
                        temp = i[s];
                        i[s] = i[2*s + b];
                        i[2*s + b] = temp;
                        s = 2*s + b;
                }
                else {
                        break;
                }
        }
}

void sorted(int* ints, int numInts){
        int b = 0;
        for (int i = 0; i < numInts - 1; i++){
                if(ints[i] > ints[i + 1]){
                        b = 1;
                }
        }
        if (b == 0){
                cout << "Yay" << endl;
        }
        else {
                cout << "Nay" << endl;
        }
}
