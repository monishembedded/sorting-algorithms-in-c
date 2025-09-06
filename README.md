#include <stdio.h>
int bubble(int arr[],int n){
    int i,j;
    for(i=0;i<n;i++)
    {
        for(j=0;j<n-i-1;j++)
        {
            if(arr[j]>arr[j+1])
            {
                int temp=arr[j];
                arr[j]=arr[j+1];
                arr[j+1]=temp;
            }
        }
        

    }
    printf("The sorted array = ");
    for(int k=0;k<n;k++){
        printf("%d ",arr[k]);
    }
}
int bin(int arr[],int n,int data){
    int low=0;
    int high=n-1;
    while(low<=high){
        int mid=low+(high-low)/2;
        if(arr[mid]==data)
        {     
                return mid;
        }
        else if(arr[mid]<data)
        {
            low=mid+1;
        }
        else
        {
            high=mid-1;
        }
    }
    return -1;
}
int main(){
    int arr[]={99,88,33,44,55,87,69,22};
    int size= sizeof(arr)/sizeof(arr[0]);
    bubble(arr,size);
    printf("\nThe Key found at the index of %d ",bin(arr,size,44));

}
