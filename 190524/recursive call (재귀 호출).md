#### 5월 24일

##  recursive call (재귀 호출)

~~~ java
	private static int power(int x, int n) {
		int result = 0;	
		if (n == 1) {
			return x;
		} else {
			return x * power(x, n-1);
		}
	}
}
~~~

this는 주소