package test;

public class test {

// 集合1...n元素,我选了6个
static int[] arr = new int[] { 1, 6, 7, 8 ,10,17};
// 选取K个,就选3个吧
static int k =4 ;
public static void main(String[] args) {
	if(k == 0) {
		System.out.println("你有没有搞错!");
		return;
	}
	int[] out = new int[k];
	int flag = 0;
	count(arr.length,flag, out);
}

static void count(int len, int flag, int[] out) {
	int j;
	for ( j = flag; j <len-k+1+flag; j++) {
		out[flag] = arr[j];
		if(flag > 0) {
			if(out[flag] <= out[flag-1]) {
				continue;
			}
		}
		if(flag == k-1 ) {
			for(int i=0; i<out.length; i++) {
				System.out.print(out[i] + ", ");
			}
			System.out.print("       ");
		}
		else {
			int newflag = flag+1;
			count(len, newflag, out);
			System.out.println();
		}
		
	}
}
}
© 2017 GitHub, Inc.
