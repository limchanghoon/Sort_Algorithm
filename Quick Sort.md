---


---

<h1 id="quick-sort">Quick Sort</h1>
<pre><code>
void quickSort(int* data, int start, int end) {
    if (start &gt;= end) {
        return;
    }

    int key = start;
    int i = start + 1, j = end, temp;

    while (i &lt;= j) {
        while (i &lt;= end &amp;&amp; data[i] &lt;= data[key]) {  //큰 값을 만날 때까지
            i++;
        }
        while (j &gt; start &amp;&amp; data[j] &gt;= data[key]) { //작은 값을 만날 때까지
            j--;
        }
        if (i &gt; j) {
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
</code></pre>

