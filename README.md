#include<stdio.h>
#include<string.h>



struct candidate
{
  char name[50];
  int votes;
};


int main ()
{
  int n, a = 0;
  struct candidate c1={"Parakh"};
  struct candidate c2={"Nabh"};
  printf ("Total no. of voters in an area : ");

  scanf ("%d", &n);
  printf("=======================================\n");
  for (int j = 0; j < n; j++){
        char x[1];
        printf("Do You Want To want (y/n) : ");
        scanf("%s", x);
        if (strcmp (x, "y") == 0){
            int age;
            printf ("Enter Your Age : ");
            scanf ("%d", &age);
          
            if (age >= 18){
                
                char d[1];
        
        
        	    for (int i = 0; i < 1; i++){
        	        
        	       
        	       
        	        
            	        printf ("Enter who you want to vote\n a)Parakh\n b)Nabh\n");
            	        scanf ("%s", d);
            	        if (strcmp (d, "a") == 0)
            		    {
                            printf("Your vote goes to Parakh\n");
                            printf("-----------------------\n");
                        
            		        a++;
            		        c1.votes = a;
            
            
            		    }
            
            	        else if (strcmp (d, "b") == 0)
            		    {
                            printf("Your vote goes to Nabh\n");
                            printf("-----------------------\n");
            		        c2.votes++;
            		    }
            	        else
            		    {
            		       printf ("Invalid Candidate\n");
            		       printf("-----------------------\n");
            		       i--;
            		    }
            
            	      }
            	        
            	   
                }
                
                else if(age<18){
                  printf ("Your are under age to vote\n");
            	  printf("=======================================\n");
            	  j--;
                    
                }
        }
            
    else{
        break;
        }
    	    
    }
    
    
    printf ("Number of votes Parakh got : %d\n", c1.votes);
  printf ("Number of votes Nabh got : %d\n", c2.votes);

  FILE *outfile, *infile;
  char z[100];

  if (c1.votes > c2.votes)
    {
      outfile = fopen ("resultdata", "w");
      char z[] = "Parakh won";
      fprintf (outfile, " %s ", z);
      fclose (outfile);
      
    }
  else if (c1.votes < c2.votes)
    {
        
        outfile = fopen ("resultdata", "w");
        char z[] = "Nabh won";
        fprintf (outfile, " %s ", z);
        fclose (outfile);
      
    }
  else
  {
        outfile = fopen ("resultdata", "w");
        char z[] = "Election result is draw";
        fprintf (outfile, " %s ", z);
        fclose (outfile);
        
  
      
  }
    char ch;
    infile = fopen ("resultdata", "r");
    while(!feof(infile))

    {

    ch=getc(infile);
    printf("%c",ch);
    
    }
    
  return 0;
}
