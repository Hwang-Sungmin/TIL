###  오름차순 내림차순

~~~ java
	// 2. Sort Asc
	public int[] asort(int[] data) {
		int temp = 0;
		for (int i = 0; i < data.length; i++) {
			for (int j = i + 1; j < data.length; j++) {
				if (data[i] > data[j]) {
					temp = data[i];
					data[i] = data[j];
					data[j] = temp;
				}
			}
		}
		return data;
	}

	// 3. Sort Desc
	public int[] dsort(int data[]) {
		int temp = 0;
		for (int i = 0; i < data.length; i++) {
			for (int j = i + 1; j < data.length; j++) {
				if (data[i] < data[j]) {
					temp = data[i];
					data[i] = data[j];
					data[j] = temp;
				}
			}
		}
		return data;
	}
}
~~~

### 2중배열 출력

``` java
public class example {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		
		int a [][] = {
				{ 2, 4, 2 },
				{ 2, 5 },
				{ 1, 3, 4, 5, 7 },
				{ 3, 3, 4, 5 }
		};
		int sum = 0;
		int hap = 0;
		for ( int temp[] : a) {
			for( int data :temp) {
			sum += data;
			}
		}
		System.out.println(sum);
		
		for(int i=0; i<a.length; i++){
			for(int j=0; j<a[i].length; j++) {
				hap += a[i][j];
			}
		}
		System.out.println(hap);		
	}
}
```

