### 数组高级冒泡排序代码

```java
public class Demo1_Array {

	/**
	 * * A:案例演示
	* 数组高级冒泡排序代码
	 */
	public static void main(String[] args) {
		int[] arr = {24, 69, 80, 57, 13};
		bubbleSort(arr);
		//selectSort(arr);
		print(arr);
	}

	/*
	 * 冒泡排序
	 * 1,返回值类型,void
	 * 2,参数列表,int[] arr
	 *
	 * 	第一次:arr[0]与arr[1],arr[1]与arr[2],arr[2]与arr[3],arr[3]与arr[4]比较4次
		第二次:arr[0]与arr[1],arr[1]与arr[2],arr[2]与arr[3]比较3次
		第三次:arr[0]与arr[1],arr[1]与arr[2]比较2次
		第四次:arr[0]与arr[1]比较1次
	 */

	public static void bubbleSort(int[] arr) {
		for (int i = 0; i < arr.length - 1; i++) {				//外循环只需要比较arr.length-1次就可以了
			for (int j = 0; j < arr.length - 1 - i; j++) {		//-1为了防止索引越界,-i为了提高效率
				if(arr[j] > arr[j+1]) {
					/*int temp = arr[j];
					arr[j] = arr[j + 1];
					arr[j+1] = temp;*/
					swap(arr,j,j+1);
				}
			}
		}
	}

	/*
	 * 打印数组
	 * 1,返回值类型void
	 * 2,参数列表int[]arr
	 */

	public static void print(int[] arr) {
		for (int i = 0; i < arr.length; i++) {
			System.out.print(arr[i] + " ");
		}
	}

	/*
	 * 选择排序
	 * 1,返回值类型void
	 * 2,参数列表int[] arr
	 *
	 * 	第一次:arr[0]分别与arr[1-4]比较,比较4次
		第二次:arr[1]分别与arr[2-4]比较,比较3次
		第三次:arr[2]分别与arr[3-4]比较,比较2次
		第四次:arr[3]与arr[4]比较,比较1次
	 */

	public static void selectSort(int[] arr) {
		for (int i = 0; i < arr.length - 1; i++) {				//只需要比较arr.length-1次
			for (int j = i + 1; j < arr.length; j++) {
				if(arr[i] > arr[j]) {
					/*int temp = arr[i];
					arr[i] = arr[j];
					arr[j] = temp;*/
					swap(arr,i,j);
				}
			}
		}
	}

	/*
	 * 换位操作
	 * 1,返回值类型,void
	 * 2,参数列表int[] arr.int i,int j
	 *
	 * 如果某个方法,只针对本类使用,不想让其他类使用就可以定义成私有的
	 */

	private static void swap(int[] arr,int i,int j) {
		int temp = arr[i];
		arr[i] = arr[j];
		arr[j] = temp;
	}
}

```
### 数组高级二分查找代码
```java
public class Demo2_Array {

	/**
	 * * A:案例演示
			* 数组高级二分查找代码
		* B:注意事项
			* 如果数组无序，就不能使用二分查找。
				* 因为如果你排序了，但是你排序的时候已经改变了我最原始的元素索引。

	 */
	public static void main(String[] args) {
		int[] arr = {11,22,33,44,55,66,77};
		System.out.println(getIndex(arr, 22));
		System.out.println(getIndex(arr, 66));
		System.out.println(getIndex(arr, 88));
	}

	/*
	 * 二分查找
	 * 1,返回值类型,int
	 * 2,参数列表int[] arr,int value
	 */

	public static int getIndex(int[] arr, int value) {
		int min = 0;
		int max = arr.length - 1;
		int mid = (min + max) / 2;

		while(arr[mid] != value) {					//当中间值不等于要找的值,就开始循环查找
			if(arr[mid] < value) {					//当中间值小于了要找的值
				min = mid + 1;						//最小的索引改变
			}else if (arr[mid] > value){			//当中间值大于了要找的值
				max = mid - 1;						//最大的索引改变
			}

			mid = (min + max) / 2;					//无论最大还是最小改变,中间索引都会随之改变

			if(min > max) {							//如果最小索引大于了最大索引,就没有查找的可能性了
				return -1;							//返回-1
			}
		}
		return mid;
	}
}
```
