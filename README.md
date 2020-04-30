# include <stdio.h>
# include <conio.h>

void main()
{
    FILE *f1,*f2;
    char file1[20],file2[20];
    char ch;
    int n;
    printf("Enter the file1 name:");
    scanf("%s",file1);
    printf("Enter the file2 name:");
    scanf("%s",file2);
    f1=fopen(file1,"r");
    f2=fopen(file2,"w");
    if(f1==NULL || f2==NULL)
    {
        printf("Cannot open file");
        exit(1);
    }
    printf("Characters to read from end of file :");
    scanf("%d",&n);
    fseek(f1,-n,SEEK_SET);
    while(!feof(f1))
    {
        ch=fgetc(f1);
        fputc(ch,f2);
    }
    getche();
}
