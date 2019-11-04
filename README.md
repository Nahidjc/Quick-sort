#include<stdio.h>
int main()
{
    int i,j,arr[10],temp,n;
    printf("Enter array size: ");
    scanf("%d",&n);
    printf("Enter array Element: ");
    for(i=0; i<n; i++)
    {
        scanf("%d",&arr[i]);
    }
    quick_sort(arr,0,n-1);
    for(i=0; i<n; i++)
    {
        printf("%d ",arr[i]);
    }
}
int quick_sort(int arr[],int start,int end)
{
    int pIndex;
    if(start<end)
    {
        pIndex=partition(arr,start,end);
        quick_sort(arr,start,pIndex-1);
        quick_sort(arr,pIndex+1,end);
    }
}
int partition(int arr[],int start,int end)
{
    int pivot,pIndex,i,temp;
    pivot=arr[end];
    pIndex=start;
    for(i=start; i<=end-1; i++)
    {
        if(arr[i]<=pivot)
        {
            temp=arr[i];
            arr[i]=arr[pIndex];
            arr[pIndex]=temp;
            pIndex=pIndex+1;

        }
    }
    temp=arr[pIndex];
    arr[pIndex]=arr[end];
    arr[end]=temp;
    return pIndex;
}
