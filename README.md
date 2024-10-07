#include <iostream>
#include <vector>
#include <string>

using namespace std;


vector<string> buildArray(vector<int>& target, int n) {
    vector<string> operations;
    int current = 1; 
    
    for (int i = 0; i < target.size(); ++i) {
        
        while (current < target[i]) {
            operations.push_back("Push");
            operations.push_back("Pop");
            ++current;  
        }
        
        operations.push_back("Push");
        ++current;
    }
    
    return operations;
}

int main() {
   
    int arr[] = {1, 3};  
    vector<int> target(arr, arr + sizeof(arr)/sizeof(arr[0])); 
    
    int n = 3;  
    
    vector<string> result = buildArray(target, n);
    
    
    cout << "Stack operations to build the target array: ";
    for (size_t i = 0; i < result.size(); ++i) {
        cout << result[i] << " ";
    }
    cout << endl;
    
    return 0;
}

