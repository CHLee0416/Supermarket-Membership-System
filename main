#include <stdio.h>
#include <stdlib.h>
#include <ctype.h>
#include <string.h>

struct customer{
	int id;
    char name[50];
    char ic[13];
    char phnNo[13];
    char grade[9];
    float points;
};
typedef struct customer customer;

struct node{
    customer cust;
    struct node *next;
};
typedef struct node node;

struct Voucher{
	char voucherName[50];
	float voucherPercentage;
}; 

typedef struct Voucher voucher;

struct Node{
	voucher data;
	struct Node *nextPtr;
};

typedef struct Node Node;

node *head=NULL;
Node *frontPtr=NULL;
float gold=0.9, platinum=0.8, diamond=0.7;
int num=1;

//Main functions
void menu(void); 
void membership(void);
void Voucher(void);
void payment(void); 
void developer(void); 

//Membership functions
void menuMember(void);
void insertMember(void); 
void modifyMember(void); 
void deleteMember(void); 
node* search(void); 
void sortMember(void);

//Voucher functions
void menuV(void);
void addV(void);
void modifyV(void);
void deleteV(void);
void displayV(void);

//Supplementary functions
void traverse(void);
void updateGrade(void);
float Bonus(void);

int main()
{
	int choice, num;
	
	menu();
	printf("\nPlease enter the choice: ");
	fflush(stdin);
	scanf("%d", &choice);
	
		
	while(choice!=5)
	{
		switch(choice)
		{
			case 1: printf("\n\n**Membership**");
				    membership();
				    break;
				    
            case 2: printf("\n\n**Payment**");	
                	payment();
                	break;
                	
            case 3: printf("\n\n**Voucher**");
					Voucher();	
            		break;
            		
            case 4: printf("\n\n**Developer**");
					 developer();	
            		 break;
            
			default: printf("Wrong choice, Please enter correct choice....\n");
					 break;
		}
		menu();
		printf("\nPlease enter the choice: ");
		fflush(stdin); //
		scanf("%d", &choice);
		
	}
	printf("\n**Exit Supermarket Membership Management System   **");
	printf("\n------------------Thank you for using our system------------------\n");

    return 0;
}

void menu(void)
{
    printf("\n     |*======================================================================*|\n");
    printf("     |*          Welcome to Supermarket Membership Management System         *|\n");
    printf("     |*======================================================================*|\n");
    printf("     |*    1.Membership                                      		     *|\n");        
    printf("     |*    2.Payment                                         		     *|\n");
    printf("     |*    3.Voucher                                         		     *|\n");
    printf("     |*    4.Developer                                       		     *|\n"); 
    printf("     |*    5.Exit                                            		     *|\n");
    printf("     |*======================================================================*|\n");
	
}

void membership()
{
	int choice, num;
	menuMember();
	printf("Please enter the choice: ");
	scanf("%d", &choice);
	
	switch(choice)
	{
		case 1: printf("\n\n**Add New Member**");
				insertMember();
			    break;
				    
		case 2: printf("\n\n**Modify Existing Member**");
				modifyMember();
			    break;
				    
		case 3: printf("\n\n**Delete Existing Member**");
				deleteMember();
			    break;
				    
		case 4: printf("\n\n**Search Existing Member**");
				search();
			    break;

        case 5: printf("\n\n**Display Existing Member**");
				sortMember();
			    break;
        	    
		case 6: break;
				    
		default: printf("Wrong choice, Please enter correct choice....\n");
				 break;	    
		}
}

void menuMember(void)
{
	printf("\n _____________________________ "
		   "\n|                             |"
	       "\n|1.Add New Member             |"
		   "\n|2.Modify Existing Member     |"
		   "\n|3.Delete Existing Member     |"
           "\n|4.Search Existing Member     |"
		   "\n|5.Display Existing Member    |"
		   "\n|6.Main Menu                  |"
		   "\n|_____________________________|\n");
}

void insertMember(){
    node *newptr, *temp;
    int valid=0;
    int len, each;
    newptr=(node*)malloc(sizeof(node));
    getchar();
    do {
        valid = 1;
        printf("\nCustomer name: ");
    	gets(newptr->cust.name);
        len = strlen ( newptr->cust.name);
        for ( each = 0; each < len; each++) 
		{
            if ( ( isdigit ( newptr->cust.name[each]))) 
			{
                valid = 0;
                printf("Error! Please input name again!");
                break;
            }
            else if( (ispunct (newptr->cust.name[each])))
            {
				valid = 0;
                printf("Error! Please input name again!");
                break;
            }
        }
        len = strlen (newptr->cust.name); 
		
			for(each = 0; each < len ; each++)
			{
				newptr->cust.name[each] = toupper(newptr->cust.name[each]);
			}
    } while ( !valid);
    

    do {
        valid = 1;
        printf("Customer IC number: ");
    	scanf("%s", &newptr->cust.ic);
        len = strlen ( newptr->cust.ic);
        if(len != 12)
        	{
                valid = 0;
                printf("Error! Please input IC again!\n");
            }
		else
		{
			for ( each = 0; each < len; each++) 
			{
	            if ( ( isalpha ( newptr->cust.ic[each]))) 
				{
	                valid = 0;
	                printf("Error! Please input IC again!\n");
	                break;
	            }
	            else if( (ispunct (newptr->cust.ic[each])))
	            {
					valid = 0;
	                printf("Error! Please input IC again!\n");
	                break;
	            }
	    	}
        }
    } while ( !valid);
    
    do {
        valid = 1;
        printf("Customer phone number: ");
    	scanf("%s", &newptr->cust.phnNo);
        len = strlen ( newptr->cust.phnNo);
         if(len < 10  || len > 12)
        	{
                valid = 0;
                printf("Error! Please input phone number again!\n");
            }
        else
		{
	        for ( each = 0; each < len; each++) 
			{
	            if ( ( isalpha ( newptr->cust.phnNo[each]))) 
				{
	                valid = 0;
	                printf("Error! Please input Phone number again!\n");
	                break;
	            }
	            else if( (ispunct (newptr->cust.phnNo[each])))
	            {
					valid = 0;
	                printf("Error! Please input phone number again!\n");
	                break;
	            }
	           
	        }
    	}
    } while ( !valid);
    
    fflush(stdin);
    strcpy(newptr->cust.grade,"Gold");    
	newptr->cust.points = 0;
    newptr->next=NULL;
    if(head==NULL){
    	head=newptr;
    	newptr->cust.id = 1;
        printf("\n\nNew member added successfully\n\n");
	}
	else{
		temp=head;
		while(temp->next!=NULL){
			temp=temp->next;
		}
		temp->next=newptr;
        num++;
		newptr->cust.id=num;
        printf("\n\nNew member added successfully\n\n");
	}
}

void modifyMember(){
    node *temp = search();
    int choice;
    int valid=0;
    int len, each;

    printf("\nCustomer detail update"
    "\n1. Name"
    "\n2. IC number"
    "\n3. Phone number"
    "\nPlease select (1/2/3): ");
    scanf("%d", &choice);
    getchar();
    switch(choice)
	{
        case 1: 
        		do {
			        valid = 1;
			        printf("\nCustomer name: ");
			    	gets(temp->cust.name);
			        len = strlen ( temp->cust.name);
        			for ( each = 0; each < len; each++) 
					{
            			if ( ( isdigit ( temp->cust.name[each]))) 
						{
                			valid = 0;
			                printf("Error! Please input name again!");
			                break;
            			}
            			else if( (ispunct (temp->cust.name[each])))
            			{
							valid = 0;
			                printf("Error! Please input name again!");
			                break;
            			}
        			}
        			len = strlen (temp->cust.name); 
		
					for(each = 0; each < len ; each++)
					{
						temp->cust.name[each] = toupper(temp->cust.name[each]);
					}
    			} while ( !valid);
    			printf("\nName has been successfully updated\n");
                break;
        case 2: 
                do {
			        valid = 1;
			        printf("Customer IC number: ");
			    	scanf("%s", &temp->cust.ic);
			        len = strlen ( temp->cust.ic);
        			if(len != 12)
        			{
		                valid = 0;
		                printf("Error! Please input IC again!\n");
            		}
					else
					{
						for ( each = 0; each < len; each++) 
						{
	            			if ( ( isalpha ( temp->cust.ic[each]))) 
							{
				                valid = 0;
				                printf("Error! Please input IC again!\n");
				                break;
	            			}
	            		
	            			else if( (ispunct (temp->cust.ic[each])))
	            			{
								valid = 0;
				                printf("Error! Please input IC again!\n");
				                break;
	            			}
	    				}
        			}
    			} while ( !valid);
    			printf("\nIC number has been successfully updated\n");
                break;
        case 3: 
                do {
			        valid = 1;
			        printf("Customer phone number: ");
			    	scanf("%s", &temp->cust.phnNo);
			        len = strlen ( temp->cust.phnNo);
			        if(len < 10  || len > 12)
        			{
		                valid = 0;
		                printf("Error! Please input phone number again!\n");
            		}
        			else
					{
	        			for ( each = 0; each < len; each++) 
						{
	            			if ( ( isalpha ( temp->cust.phnNo[each]))) 
							{
				                valid = 0;
				                printf("Error! Please input Phone number again!\n");
				                break;
	            			}
	            			else if( (ispunct (temp->cust.phnNo[each])))
	           				{
								valid = 0;
				                printf("Error! Please input phone number again!\n");
				                break;
	            			}
	           
	        			}
    				}
    			} while ( !valid);
    			printf("\nPhone Number has been successfully updated\n");
                break;
        default:printf("\nInvalid choice");
                break;
    }   
}

void sortMember()
{	int ch;
	node *current = head, *temp = NULL;  
   	customer index;
   	
	printf("\n _____________________________ "
		   "\n|                             |"
		   "\n|1.Sort by ID Number          |"
		   "\n|2.Sort by Names              |"
		   "\n|3.Sort by Points             |"
		   "\n|4.Main menu                  |"
		   "\n|_____________________________|\n");
	printf("\nPlease enter your choice: ");
	if (scanf("%d", &ch))
	{
		fflush(stdin);
		switch (ch)
			{
				case 1: printf("Details of ID Number:");
						if(head == NULL) {  
		            		printf("\nNo member! Please insert a new member!\n");  
		            		return;
		        		}  
		        		else {  
		            		while(current != NULL) {  
		                //Node index will point to node next to current  
		                		temp = current->next;
				
		                		while(temp != NULL) {  
		                    		//If current node's data is greater than index's node data, swap the data between them  
		                    		if(current ->cust.id > temp ->cust.id) {  
				                        index= current->cust;  
				                        current->cust= temp->cust;  
				                        temp->cust = index;  
		                    		}  
		                    		temp = temp->next;  
		                		}  
		                		current = current->next;  	
		            		} 	
		            	} traverse();
		            	break;  
					
				case 2: printf("Details of member's name:");
						
		        		if(head == NULL) {  
		        			printf("\nNo member! Please insert a new member!\n");  
		            		return;  
		        		}  
		        		else {  
		            		while(current != NULL) {  
		                //Node index will point to node next to current  
		                		temp = current->next;
				
		                		while(temp != NULL) {  
		                    		//If current node's data is greater than index's node data, swap the data between them  
		                    		if(strcmp(current->cust.name, temp->cust.name )>0) {  
				                        index= current->cust;  
				                        current->cust= temp->cust;  
				                        temp->cust = index;  
		                    		}  
		                    		temp = temp->next;  
		                		}  
		                		current = current->next;  	
		            		} 	
		            	} traverse();
		            	break; 
		            	
		    	case 3: printf("Details of member's points:");
						
		        		if(head == NULL) { 
							printf("\nNo member! Please insert a new member!\n");   
		            		return;  
		        		}  
		        		else {  
		            		while(current != NULL) {  
		                //Node index will point to node next to current  
		                		temp = current->next;
				
		                		while(temp != NULL) {  
		                    		//If current node's data is smaller than index's node data, swap the data between them  
		                    		if(current ->cust.points < temp ->cust.points) {  
				                        index= current->cust;  
				                        current->cust= temp->cust;  
				                        temp->cust = index;  
		                    		}  
		                    		temp = temp->next;  
		                		}  
		                		current = current->next;  	
		            		} 	
		            	} traverse();
		            	break;
		        case 4: main();
		        
				default:printf("Wrong choice! Please enter correct choice!");
						sortMember();
						break;	 
		    }
	}
	else
	{
		printf("\nWrong Choice !");
		fflush(stdin);
		sortMember();
	}
}


void traverse(){
    node *temp;
    temp = head;

    printf("\n\n_______________________________________________Information of the member_______________________________________________");
    printf("\n\n|================================================================================================================|\n");
    printf("|ID\t\tNames\t\t\t    IC\t\t\tPhone Number\t\tGrade\t\t  Points |");
    printf("\n|----------------------------------------------------------------------------------------------------------------|");
    while(temp!=NULL){
    	printf("\n|#%04d   %-25s     %-15s          %-16s        %-8s       %8.2f  | ", temp->cust.id, temp->cust.name, temp->cust.ic, temp->cust.phnNo, temp->cust.grade, temp->cust.points);
    	temp= temp-> next; 
    }
	printf("\n|================================================================================================================|\n");
    printf("\n__________________________________________________________End_________________________________________________________\n\n");       	
}

void deleteMember(){
    node *temp, *prev, *curr;
    int i, deleteId;
    char confirm;

	temp = search();
	fflush(stdin);
    if(head->cust.id==temp->cust.id){
        printf("\nConfirm delete?(Y/N)->");
        scanf("%c", &confirm);
        if(toupper(confirm)=='Y'){
            head=head->next;
            temp->next=NULL;
            free(temp);
            printf("\nThe member has been deleted\n");
        }
        else{
        	printf("\nDelete unsuccessful.\n");	
		}
    }
    else{
    	prev=head;
        curr=head->next;
	    while(curr!=NULL){
	        if(curr->cust.id==temp->cust.id){
	            break;
	        }
	        prev=curr;
            curr=curr->next;
		}
	    printf("\nConfirm delete?(Y/N)->");
	    scanf("%c", &confirm);
	    if(toupper(confirm)=='Y'){
	        prev->next=temp->next;
	        temp->next=NULL;
	        free(temp);
	    	printf("The member has been deleted\n");
	    }
	    else{
        	printf("\nDelete unsuccessful.\n");	
		}
	}	
}

void payment(){
	float bonus, total=0;
    char confirm, apply;
    printf("\n\nTotal : ");
    fflush(stdin);
    if(scanf("%f", &total) && total >0)
	{
   	fflush(stdin);
    printf("\nMember?(Y/N) : ");
    scanf("%c", &confirm);
    if(toupper(confirm)=='Y'){
        node* member = search();       
		if(strcmp(member->cust.grade,"Gold")==0){
        	printf("\nMember: Gold");
            member->cust.points += (total/10);
            printf("\nApply voucher?(Y/N) : ");
            fflush(stdin);
    		scanf("%c", &apply);
    		if(toupper(apply)=='Y')
    		{
				bonus = Bonus();
            	total = total * (gold-bonus);
            	printf("\nTotal after discount = %.2f\n", total);  			
			}
			else if(toupper(apply)=='N')
			{
				total = total * (gold-bonus);
            	printf("\nTotal after discount = %.2f\n", total); 				
			}
        }
        else if (strcmp(member->cust.grade,"Platinum")==0){
        	printf("\nMember: Platinum");
            member->cust.points += (total/10);
            printf("\nApply voucher?(Y/N) : ");
            fflush(stdin);
    		scanf("%c", &apply);
    		if(toupper(apply)=='Y')
    		{
				bonus=Bonus();
            	total = total * (platinum-bonus);
            	printf("\nTotal after discount = %.2f\n", total);  			
			}
			else if(toupper(apply)=='N')
			{
				total = total * (platinum-bonus);
            	printf("\nTotal after discount = %.2f\n", total); 				
			}
        }
        else if (strcmp(member->cust.grade,"Diamond")==0){
        	printf("\nMember: Diamond");
            member->cust.points += (total/10);
            printf("\nApply voucher?(Y/N) : ");
            fflush(stdin);
    		scanf("%c", &apply);
    		if(toupper(apply)=='Y')
    		{
				bonus=Bonus();
            	total = total * (diamond-bonus);
            	printf("\nTotal after discount = %.2f\n", total);  			
			}
			else if(toupper(apply)=='N')
			{
				total = total * (diamond-bonus);
            	printf("\nTotal after discount = %.2f\n", total); 				
			}
        }
        else{
            printf("\nMember not found");
        }
        updateGrade();	         	
		}	
    else{
    	printf("\nPlease become a member to get a discount.\n");
        printf("\nTotal = %.2f\n", total);
		}
	
}
	else{
		printf("\nPlease input the correct amount!\n");
		payment();
	}
}

node* search(void)
{
	int s, ID;
	char n[50], IC[13],phone[12];
	node *temp;
	temp = head;
	int len1, each1,valid1;
    
	printf("\n _____________________________ "
		   "\n|                             |"
	       "\n|1.Search by Name             |"
		   "\n|2.Search by ID Number        |"
		   "\n|3.Search by IC Number        |"
		   "\n|4.Search by Phone Number     |"
		   "\n|5.Main Menu                  |"		   
		   "\n|_____________________________|\n");
	printf("\nPlease enter your choice: ");
	fflush(stdin);
	scanf("%d", &s);
	
			
	if(s==1)
	{
	do{
		valid1 = 1;
		printf("\nPlease enter member's name: ");
		fflush(stdin);
		gets(n);
		len1 = strlen(n);
		for(each1 = 0; each1 < len1; each1++)
		{
			if((isdigit(n[each1])))
			{
				valid1 = 0;
				printf("Error! Please enter name again!\n");
				break;
			}
			else if((ispunct(n[each1])))
			{
				valid1 = 0;
				printf("Error! Please enter name again!\n");
				break;
			}
									
			for(each1 = 0; each1 < len1 ; each1++)
			{
				n[each1] = toupper(n[each1]);
			}
		}
	}while(!valid1);
		
		while(temp!=NULL&&strcmp(temp->cust.name,n)!=0)
		{
			temp=temp->next;
		}
		if(temp!=NULL&&strcmp(temp->cust.name,n)==0)
		{
        	printf("\nCustomer name: %s", temp->cust.name);
        	printf("\nCustomer ID: #%04d", temp->cust.id);
        	printf("\nCustomer IC number: %s", temp->cust.ic);
        	printf("\nCustomer phone number: %s", temp->cust.phnNo);
        	printf("\nCustomer grade: %s", temp->cust.grade);
        	printf("\nCustomer points: %.2f\n", temp->cust.points);
            return temp;
		}
		else
		{
			printf("\nMember not found!!\n");
			search();
		}	
	}
	else if(s==2)
	{
		printf("\nPlease enter the member's ID number: ");
		scanf("%d", &ID);
		
		while(temp!=NULL&&temp->cust.id!=ID)
		{
			temp=temp->next;
		}
		if(temp!=NULL&&temp->cust.id==ID)
		{
        	printf("\nCustomer ID: #%04d", temp->cust.id);
			printf("\nCustomer name: %s", temp->cust.name);
        	printf("\nCustomer IC number: %s", temp->cust.ic);
        	printf("\nCustomer phone number: %s", temp->cust.phnNo);
        	printf("\nCustomer grade: %s", temp->cust.grade);
        	printf("\nCustomer points: %.2f\n", temp->cust.points);
            return temp;
		}
		else
		{
			printf("\nMember not found!!\n");
			search();
		}
	}
	else if(s==3)
	{
		printf("\nPlease enter the member's IC number: ");
		scanf("%s", &IC);
		
		while(temp!=NULL&&strcmp(temp->cust.ic,IC)!=0)
		{
			temp=temp->next;
		}
		if(temp!=NULL&&strcmp(temp->cust.ic,IC)==0)
		{
        	printf("\nCustomer IC number: %s", temp->cust.ic);
        	printf("\nCustomer ID: #%04d", temp->cust.id);
			printf("\nCustomer name: %s", temp->cust.name);
        	printf("\nCustomer phone number: %s", temp->cust.phnNo);
        	printf("\nCustomer grade: %s", temp->cust.grade);
        	printf("\nCustomer points: %.2f\n", temp->cust.points);
            return temp;
		}
		else
		{
			printf("\nMember not found!!\n");
			search();	
		}	
	}
	else if(s==4)
	{
		printf("\nPlease enter the member's phone number: ");
		scanf("%s", &phone);
		
		while(temp!=NULL&&strcmp(temp->cust.phnNo,phone)!=0)
		{
			temp=temp->next;
		}
		if(temp!=NULL&&strcmp(temp->cust.phnNo,phone)==0)
		{
        	printf("\nCustomer phone number: %s", temp->cust.phnNo);
        	printf("\nCustomer ID: #%04d", temp->cust.id);
			printf("\nCustomer name: %s", temp->cust.name);
        	printf("\nCustomer IC number: %s", temp->cust.ic);
        	printf("\nCustomer grade: %s", temp->cust.grade);
        	printf("\nCustomer points: %.2f\n", temp->cust.points);
            return temp;
		}
		else
		{
			printf("\nMember not found!!\n");
			search();			
		}	
	}
	else if(s==5)
	{
		main();
	}
	else
	{
		printf("\nWrong choice!\n");
		search();
	}
}

void Voucher()
{
	int choice, num;
	menuV();
	printf("Please enter the choice: ");
	scanf("%d", &choice);
	
	switch(choice)
	{
		case 1: printf("\n\n**Add New Voucher**");
				addV();
			    break;
				    
		case 2: printf("\n\n**Modify Existing Voucher**");
				modifyV();
			    break;
				    
		case 3: printf("\n\n**Delete Existing Voucher**");
				deleteV();
			    break;
				    
		case 4: printf("\n\n**Display Existing Voucher**");
				displayV();
			    break;
			    
		case 5: break;
				    
		default: printf("Wrong choice. Please enter correct choice....\n");
				 break;	    
		}
	
}

void menuV(void)
{
	printf("\n _____________________________ "
		   "\n|                             |"
	       "\n|1.Add New Voucher            |"
		   "\n|2.Modify Existing Voucher    |"
		   "\n|3.Delete Existing Voucher    |"
		   "\n|4.Display Existing Voucher   |"
		   "\n|5.Main Menu                  |"
		   "\n|_____________________________|\n");
}

void addV(void)
{
	Node *newPtr, *tempPtr;
    newPtr = (Node*)malloc(sizeof(Node));
	newPtr->nextPtr = NULL;	
    getchar();
    printf("\n\nVoucher Name: ");
    gets(newPtr->data.voucherName);
    printf("Voucher Percentage: ");
    scanf("%f", &newPtr->data.voucherPercentage);
    fflush(stdin);
    
	if(frontPtr==NULL)
	{
		frontPtr = newPtr;
	}
	else
	{
		newPtr->nextPtr = frontPtr;
		frontPtr = newPtr;
	}
	printf("\nAdded successful!\n");  
	
}

void modifyV()
{
	Node *tempPtr;
    char vName[50];
	int choice;
	tempPtr=frontPtr;
	getchar();   
	printf("\n\nVoucher Name: ");
    gets(vName);

	while(tempPtr!=NULL&& strcmp(vName,tempPtr->data.voucherName)!=0)
	{
		tempPtr=tempPtr->nextPtr;
	}
	if(tempPtr!=NULL&& strcmp(vName,tempPtr->data.voucherName)==0)
	{
		printf("\nModified voucher detail");
		printf("\n-------------------------");
        printf("\nVoucher Name: %s", tempPtr->data.voucherName);
    	printf("\nVoucher Percentage: %.2f", tempPtr->data.voucherPercentage);
    	
    	printf("\n\nYou can only modify the percentage. ");    	
        printf("\nVoucher Percentage: ");
        scanf("%f", &tempPtr->data.voucherPercentage);
        printf("\nModify successful!\n");  
	}
	else
	{
		printf("No such Voucher.Please enter the correct voucher name or add a new voucher.\n");
		Voucher();
	}	
}

void displayV(void)
{
	Node *tempPtr;
    tempPtr = frontPtr;
    
	if(tempPtr==NULL)
	{
		printf("\nThere is no voucher. Please add a new voucher.\n");
	}
	else if(tempPtr!=NULL)
	{
    	printf("\n\n__________________________Information of the voucher__________________________");
    	printf("\n\n|============================================================================|\n");
    	printf("|         %-21s          |          %-25s|", "Voucher Names", "Percentage");
    	printf("\n|----------------------------------------------------------------------------|");
    	while(tempPtr!=NULL)
		{
    		printf("\n|         %-21s          |            %-23.2f| ", tempPtr->data.voucherName, tempPtr->data.voucherPercentage);
        	tempPtr = tempPtr->nextPtr; 
    	}
		printf("\n|============================================================================|\n");
    	printf("\n______________________________________End______________________________________\n\n"); 	
	}
}

void deleteV(void)
{
	Node *tempPtr, *prevPtr, *currPtr;
	char deleteName[50];
    char confirm;
	getchar();    
	printf("\n\nVoucher Name: ");
    gets(deleteName);
	
	//delete first node
	if(frontPtr==NULL)
	{
		printf("There is no voucher. Please add a new voucher.\n");
	}
	else if(frontPtr!=NULL && strcmp(deleteName,frontPtr->data.voucherName)==0)
	{
		tempPtr = frontPtr;
		printf("\nDeleted voucher detail");
		printf("\n-------------------------");
        printf("\nVoucher Name: %s", tempPtr->data.voucherName);
    	printf("\nVoucher Percentage: %.2f", tempPtr->data.voucherPercentage);
	    printf("\n\nConfirm delete?(Y/N)->");
	    scanf("%c", &confirm);
	    if(toupper(confirm)=='Y'){
			frontPtr = frontPtr->nextPtr;
			free(tempPtr);
			printf("\nThe voucher is deleted\n");
		}
		else
		{
			printf("\nDelete unsuccessful.\n");
		}			
	}
	else
	{
		prevPtr = frontPtr;
		currPtr = frontPtr->nextPtr;
		
		//find the position of the node
		while(currPtr!=NULL && strcmp(deleteName,currPtr->data.voucherName)!=0)
		{
			prevPtr = currPtr;
			currPtr = currPtr->nextPtr;
		}
		
		if(currPtr!=NULL && strcmp(deleteName,currPtr->data.voucherName)==0)
		{
			tempPtr = currPtr;
			printf("\nDeleted voucher detail");
	    	printf("\n-------------------------");
        	printf("\n\nVoucher Name: %s", tempPtr->data.voucherName);
        	printf("\nVoucher Percentage: %.2f", tempPtr->data.voucherPercentage);
	    	printf("\n\nConfirm delete?(Y/N)->");
	    	scanf("%c", &confirm);
	    	if(toupper(confirm)=='Y'){
				prevPtr->nextPtr = currPtr->nextPtr;
				free(tempPtr);
				printf("\nThe voucher is deleted\n");
			}
		}
		else
		{
			printf("\nNo such Voucher.Please enter the correct voucher name.");
			Voucher();
		}
	}
}

float Bonus(void)
{
	float bonus = 0;
	Node *tempPtr= frontPtr;
	char sName[50];
	getchar();    
	printf("\nVoucher Name: ");
    gets(sName);
	
	while(tempPtr!=NULL&& strcmp(sName,tempPtr->data.voucherName)!=0)
	{
		tempPtr=tempPtr->nextPtr;
	}
	if(tempPtr==NULL)
	{
		printf("\nThere is no voucher. Please add a new voucher.\n");
	}
	else if(tempPtr!=NULL&& strcmp(sName,tempPtr->data.voucherName)==0)
	{
		bonus+=(tempPtr->data.voucherPercentage/100);
	}
	return bonus;
}

void updateGrade(void){
    node *temp = head;
    while(temp!=NULL){
		if(temp->cust.points>=1501)
		{
			strcpy(temp->cust.grade,"Diamond");
		}
		else if(temp->cust.points>=501)
		{
			strcpy(temp->cust.grade, "Platinum");
		}
		else if(temp->cust.points>=0)
		{
			strcpy(temp->cust.grade, "Gold");
		}
        temp = temp->next;
	}
}

void developer(void)
{	
	printf("\nStudents Group 5 Data Structure (BIC10404): \n");

	printf("\n1. Name         : Lee Chee Hui"
		   "\n   Matric Number: AI210348"
		   "\n   Section      : 13\n");
		   
	printf("\n2. Name         : Lieu Yee Zhe"
		   "\n   Matric Number: AI210369"
		   "\n   Section      : 13\n");
		   
	printf("\n3. Name         : Chai Xiao Hui"
		   "\n   Matric Number: AI210319"
		   "\n   Section      : 13\n");   
}
