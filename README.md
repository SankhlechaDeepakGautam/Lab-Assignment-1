# Lab-Assignment-1
Email App assignment with do while loop
package com.mail.driver;


import java.io.IOException;

import com.email.model.Employee;
import com.email.service.CredentialService;

public class Driver {

	public static void main(String[] args) throws IOException {
		
		Employee employee = new Employee("Deepak","Sankhlecha");
		CredentialService credentialService= new CredentialService(); 
		String generatedEmail = null;
		char[] generatedpwd;
		
		int option;
		
	// To display the options to the User.
		
	   do { 
		   
		System.out.println("Please Enter the department from the following");
		System.out.println("1. Technical");
		System.out.println("2. Admin");
		System.out.println("3. Human resource");
		System.out.println("4. Legal");
		
		option = (int) System.in.read();
		
		} while ( option <'1'|| option >'4'); 
		
	// Now , Use of if - else if statements to choose among multiple options.
		
		switch (option) { 
		
		case'1':
			generatedEmail=credentialService.generateEmailAddress(employee.getFirstName(),employee.getLastName(),"tech");
            break;			
		case'2':
			generatedEmail=credentialService.generateEmailAddress(employee.getFirstName(),employee.getLastName(),"admin");
			break;
		case'3':
		    generatedEmail=credentialService.generateEmailAddress(employee.getFirstName(),employee.getLastName(),"hr");
		    break;
		case'4':
			generatedEmail=credentialService.generateEmailAddress(employee.getFirstName(),employee.getLastName(),"legal");
		    break;
		default:
			System.out.println("Enter a valid Option");
		
			System.exit(-1);
			}

		generatedpwd=credentialService.generatePassword();
		credentialService.showCredentials(employee.getFirstName(),generatedEmail ,generatedpwd );
	
		
		
	}

}
