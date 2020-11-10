#include<iostream>
using namespace std;
int check_convert_value(int num);
void find_sum_minimun_absloute(int array[],int size,int&index,int&index2);
int main()
{
	int index = 0;
	int index2 = 0;
	int array[6] = { -5, 2, 4, -3, 1, 9 };
	int size = 6;
	find_sum_minimun_absloute(array,size,index,index2);
	cout << array[index] << endl;
	cout << array[index2] << endl;
}
void find_sum_minimun_absloute(int array[], int size, int&index, int&index2)
{
	int value = 0;
	int value2 = 0;
	int temp = 0;
	value = array[0];
	value2 = array[1];
	temp = value + value2;
	index = 0;
	index2 = 1;
	for (int i = 1; i < size; i++)
	{
		value=check_convert_value(array[i]);

		if (i + 1 < size)
		{
			for (int j = i + 1; j < size; j++)
			{
				value2 = check_convert_value(array[j]);
				if (value + value2 < temp)
				{
					temp = value + value2;
					index = i;
					index2 = j;
				}
			}
		}
	}
}
int check_convert_value(int num)
{
	if (num< 0)
	{
		num =num* -1;
	}
	return num;
}