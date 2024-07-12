// Name- Prerana Rajesh Gajare      Class-SEIT      RollNo-SI41  
/*
 * 1.	Book Shop Inventory
		Problem Statement: A book shop maintains the inventory of books that are being sold at the shop. The list includes details such as
	    author, title, prize, publisher and stock position. Whenever customer wants a book, the sale person inputs the title and author 
	    and system searches the list and display whether it is available or not. If it is not, an appropriate message is displayed. If it
	    is, the system displays the book details and request for the number of copies required. If the required copies are available, the
	    total cost of the requested copies is displayed; otherwise the message “Required copies not in stock” is displayed.
*/
//Source code:-
import java.util.*;

class book
{
		int n=20;

	  	 String[] title = new String[n];
	     String[] author = new String[n];
	     String[] Publisher = new String[n];
	     int[] price = new int[n];
	     int[] Stock_position = new int[n];

	
	public void getdata(int n)
	{
		Scanner sc = new Scanner(System.in);
		for(int l=0;l<n;l++)
		{
		System.out.println("\nEnter The Title Of Book :");
		title[l]=sc.next();
		System.out.println("\nEnter The Author Of Book :");
		author[l]=sc.next();
		System.out.println("\nEnter The Publisher Of Book :");
		Publisher[l]=sc.next();
		System.out.println("\nEnter The Number Of Books Added :");
		Stock_position[l]=sc.nextInt();
		System.out.println("\nEnter The Cost Of 1 Copy :");
		price[l]=sc.nextInt();
		
		}
	}
	
	public void display(int n)
	{
		System.out.println("Author \t Title \t Price \t Publisher \t Stock_position");
        for(int i=0;i<n;i++)
         {
        	System.out.println(author[i]+" \t "+title[i]+" \t "+price[i] +" \t "+Publisher[i]+" \t "+Stock_position[i]);
          }
		
	}
	
	
	public void search(int n)
	{
		Scanner sc = new Scanner(System.in);
		String item;
		 String tit;
			
		   
		    System.out.println("\nSearch the record");
		    System.out.println("\nEnter the name of author");
		    item=sc.next();
		    System.out.println("\nEnter the title of book");
		    tit=sc.next();
			int l1=0;
			 for(int k=0;k<n;k++)
			  {
				 int m;
				double totalcost;
					if(item.equals(author[k]) && tit.equals(title[k]))
					{
					    System.out.println("\nThe book is available");
					    System.out.println("Author \t Title \t Price \t Publisher \t Stock_position");
					    System.out.println(author[k]+" \t "+title[k]+" \t "+price[k] +" \t "+Publisher[k]+" \t "+Stock_position[k]);
			   		    System.out.println("\nEnter the no of copies required");
					    m=sc.nextInt();

					    if(m<=Stock_position[k])
					    {
					    	
					    	totalcost=price[k]*m;
						    System.out.println("\nThe total cost of requested copies is:"+totalcost);
					    }
					    else
					    {
						    System.out.println("Required copies not in stock");

					    }
					    
					    	l1=1;
					       break;
				       }
			  }
		 	          
			         if(l1==0)
			         {
				        System.out.println("\nBook is not available.");
				    
			         }
}
}

public class sample1
{
	public static void main(String[] args) 
	{
		Scanner sc = new Scanner(System.in);
		int l,n;
		System.out.println("\nEnter the number of books you want :");
		n = sc.nextInt();
		book obj = new book();
		do
		{			
			
			System.out.println("\nEnter the operation to be performed:\n1)Insert\n2)Display\n3)Search\n4)Exit\n(1,2,3,4)");
			l = sc.nextInt();
			switch(l)
			{
				case 1:
				
					obj.getdata(n);
					break;
				case 2:				
					obj.display(n);
					break;
				case 3:
					obj.search(n);
					break;
				case 4:
					System.out.println("The End");
					break;
				default:
					System.out.println("Wrong Choice");
				
			}
		}while(l != 4);
	}
}
*************************************************************************************************OUTPUT*****************************************************************************************************

Enter the number of books you want :
3

Enter the operation to be performed:
1)Insert
2)Display
3)Search
4)Exit
(1,2,3,4)
1

Enter The Title Of Book :
TheGuide

Enter The Author Of Book :
RKNarayan

Enter The Publisher Of Book :
VickingPress

Enter The Number Of Books Added :
5

Enter The Cost Of 1 Copy :
376

Enter The Title Of Book :
MalgudiDays

Enter The Author Of Book :
RKNarayan

Enter The Publisher Of Book :
Thoughtpubl

Enter The Number Of Books Added :
4

Enter The Cost Of 1 Copy :
178

Enter The Title Of Book :
Untouchable

Enter The Author Of Book :
MulkRajAnand

Enter The Publisher Of Book :
PenguinClassic

Enter The Number Of Books Added :
6

Enter The Cost Of 1 Copy :
133

Enter the operation to be performed:
1)Insert
2)Display
3)Search
4)Exit
(1,2,3,4)
2
Author 	 Title 	 Price 	 Publisher 	 Stock_position
RKNarayan 	 TheGuide 	 376 	 VickingPress 	 5
RKNarayan 	 MalgudiDays 	 178 	 Thoughtpubl 	 4
MulkRajAnand 	 Untouchable 	 133 	 PenguinClassic 	 6

Enter the operation to be performed:
1)Insert
2)Display
3)Search
4)Exit
(1,2,3,4)
3

Search the record

Enter the name of author
RKNarayan

Enter the title of book
TheGuide

The book is available
Author 	 Title 	 Price 	 Publisher 	 Stock_position
RKNarayan 	 TheGuide 	 376 	 VickingPress 	 5

Enter the no of copies required
3

The total cost of requested copies is:1128.0

Enter the operation to be performed:
1)Insert
2)Display
3)Search
4)Exit
(1,2,3,4)
4
The End
