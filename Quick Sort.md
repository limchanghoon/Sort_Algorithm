# Quick Sort

```c++

void quickSort(int* data, int start, int end) {
    if (start >= end) {
        return;
    }

    int key = start;
    int i = start + 1, j = end, temp;

    while (i <= j) {
        while (i <= end && data[i] <= data[key]) {  //큰 값을 만날 때까지
            i++;
        }
        while (j > start && data[j] >= data[key]) { //작은 값을 만날 때까지
            j--;
        }
        if (i > j) {
            temp = data[j];
            data[j] = data[key];
            data[key] = temp;
        }
        else {
            temp = data[i];
            data[i] = data[j];
            data[j] = temp;
        }
    }
 
    quickSort(data, start, j - 1);
    quickSort(data, j + 1, end);
}
```

