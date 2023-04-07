# CTDL-GT_Heap_Sort_1.cpp
Heap Sort
Nguồn tham khảo : https://funix.edu.vn/chia-se-kien-thuc/gioi-thieu-ve-thuat-toan-heap-sort/
Cài đặt : 

void heapify(int arr[], int n, int i)
{
    int largest = i; // Initialize largest as root Since we are using 0 based indexing
    int left = 2 * i + 1;
    int right = 2 * i + 2; 
 
    // If left child is larger than root
    if (left < n && arr[l] > arr[largest])
        largest = left;
 
    // If right child is larger than largest so far
    if (right  < n && arr[r] > arr[largest])
        largest = right;
 
    // If largest is not root
    if (largest != i) {
        swap(arr[i], arr[largest]);
 
        // Recursively heapify the affected sub-tree
        heapify(arr, n, largest);
    }
}
void heapSort(int arr[], int n)
{
    // Build heap (rearrange array)
    for (int i = n / 2 - 1; i >= 0; i--)
        heapify(arr, n, i);
 
    // One by one extract an element from heap
    for (int i = n - 1; i >= 0; i--) {
        // Move current root to end
        swap(arr[0], arr[i]);
 
        // call max heapify on the reduced heap
        heapify(arr, i, 0);
    }
}
