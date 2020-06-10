import java.util.*;

interface Chennai {
	String city = "CHENNAI";
	String incharge = "Vimal";
	String contact = "+91 9003478223";
	HashMap<String,String> client = new HashMap<String,String>();
	int available = client.size();
	public abstract void printCh();
}

interface Coimbatore {
	String city = "COIMBATORE";
	String incharge = "Adhil";
	String contact = "+91 7092618727";
	HashMap<String,String> client = new HashMap<String,String>();
	int available = client.size();
	public abstract void printCo();
}

interface Trichy {
	String city = "TRICHY";
	String incharge = "Sathish";
	String contact = "+91 6380281881";
	HashMap<String,String> client = new HashMap<String,String>();
	int available = client.size();
	public abstract void printTr();
}

interface Madurai {
	String city = "MADURAI";
	String incharge = "Sanjeev";
	String contact = "+91 9080383200";
	HashMap<String,String> client = new HashMap<String,String>();
	int available = client.size();
	public abstract void printMa();
}

class Location implements Chennai, Coimbatore, Trichy, Madurai {
	
	static private int location;
	private char ch;
	int[] available = {Chennai.available, Coimbatore.available, Trichy.available, Madurai.available};
	String[] name = {Chennai.city, Coimbatore.city, Trichy.city, Madurai.city};
	String[] incharge = {Chennai.incharge, Coimbatore.incharge, Trichy.incharge, Madurai.incharge};
	String[] contact = {Chennai.contact, Coimbatore.contact, Trichy.contact, Madurai.contact};
	HashMap<Integer,String> password = new HashMap<Integer,String>(); 
	HashMap<String,String> clientCh = Chennai.client;
	HashMap<String,String> clientCo = Coimbatore.client;
	HashMap<String,String> clientTr = Trichy.client;
	HashMap<String,String> clientMa = Madurai.client;
	void getlocation(int location) {
		this.location = location;
	}
	void putPassword(String[] availableLocation) {
		for(int i=0;i<availableLocation.length;i++) {
			this.password.put(i, availableLocation[i]);
		}
	}
	public void printCh() {
		for (String name: clientCh.keySet()){
            String key = name.toString();
            String value = clientCh.get(name).toString();  
            System.out.println(key + " " + value);  
		}

	}
	public void printCo() {
		for (String name: clientCo.keySet()){
            String key = name.toString();
            String value = clientCo.get(name).toString();  
            System.out.println(key + " " + value);  
		}

	}
	public void printTr() {
		for (String name: clientTr.keySet()){
            String key = name.toString();
            String value = clientTr.get(name).toString();  
            System.out.println(key + " " + value);  
		}

	}
	public void printMa() {
		for (String name: clientMa.keySet()){
            String key = name.toString();
            String value = clientMa.get(name).toString();  
            System.out.println(key + " " + value);  
		}

	}
	void initialize() {
		clientCh.put("Ram", "+91 9876543210");
		clientCh.put("Sita", "+91 9876543210");
		clientCo.put("Ameer", "+91 9876543210");
		clientCo.put("Nisha", "+91 9876543210");
		clientTr.put("Sahul", "+91 9876543210");
		clientTr.put("Sahul", "+91 9876543210");
		clientMa.put("Anjali", "+91 9876543210");
		clientMa.put("Mira", "+91 9876543210");
		
	}
	void execute() {
		Scanner sc = new Scanner(System.in);
		if(location > 0 && location < 5) {
			System.out.println("----------------------------------------------------------------------" +
					"\n1.Admin Pannel (Authentication Required)" +
					"\n2.Customer Pannel" +
					"\n----------------------------------------------------------------------");
			int choice = sc.nextInt();
			if(choice == 1) {
				System.out.println("\nEnter the Password:");
				String pass = sc.next();
				if(pass.equals(password.get(location-1))) {
					System.out.println("Password Matched..!");
					if(location == 1) { 
						System.out.println("\n----------------------------------------------------------------------" +
								"\nWelcome Admin of "+ Chennai.city +" Mr. "+ Chennai.incharge +
								"\nProperty Available : " + available[0] +
								"\n----------------------------------------------------------------------");
						printCh();
						ch = 'y';
						while(ch=='y') {
							System.out.println("Do You Want To Add a property in Your City...? (y/n)");
							ch = sc.next().charAt(0);
							if(ch == 'y') {
								System.out.println("Enter the Name and Contact Number of the Owner");
								String name = sc.next();
								String contacts = "+91" + sc.next();
								clientCh.put(name, contacts);
								available[location-1] = clientMa.size();
							}
						}
						
					} else if (location == 2) {
						System.out.println("\n----------------------------------------------------------------------" +
								"\nWelcome Admin of "+ Coimbatore.city +" Mr. "+ Coimbatore.incharge +
								"\nProperty Available : " + available[1] +
								"\n----------------------------------------------------------------------");
						printCo();
						ch = 'y';
						while(ch=='y') {
							System.out.println("Do You Want To Add a property in Your City...? (y/n)");
							ch = sc.next().charAt(0);
							if(ch == 'y') {
								System.out.println("Enter the Name and Contact Number of the Owner");
								String name = sc.next();
								String contacts = "+91" + sc.next();
								clientCo.put(name, contacts);
								available[location-1] = clientMa.size();
							}
						}
						
					} else if (location == 3) {
						System.out.println("\n----------------------------------------------------------------------" +
								"\nWelcome Admin of "+ Trichy.city +" Mr. "+ Trichy.incharge +
								"\nProperty Available : " + available[2] +
								"\n----------------------------------------------------------------------");
						printTr();
						ch = 'y';
						while(ch=='y') {
							System.out.println("Do You Want To Add a property in Your City...? (y/n)");
							ch = sc.next().charAt(0);
							if(ch == 'y') {
								System.out.println("Enter the Name and Contact Number of the Owner");
								String name = sc.next();
								String contacts = "+91" + sc.next();
								clientTr.put(name, contacts);
								available[location-1] = clientMa.size();
							}
						}
						
					} else if (location == 4) {
						System.out.println("\n----------------------------------------------------------------------" +
								"\nWelcome Admin of "+ Madurai.city +" Mr. "+ Madurai.incharge +
								"\nProperty Available : " + available[3] +
								"\n----------------------------------------------------------------------");
						printMa();
						ch = 'y';
						while(ch=='y') {
							System.out.println("Do You Want To Add a property in Your City...? (y/n)");
							ch = sc.next().charAt(0);
							if(ch == 'y') {
								System.out.println("Enter the Name and Contact Number of the Owner");
								String name = sc.next();
								String contacts = "+91" + sc.next();
								clientMa.put(name, contacts);
								available[location-1] = clientMa.size();
							}
						}
					}		
					
				} else {
					System.out.println("Wrong Password..!");
				}
			} else if(choice == 2) {
				System.out.println("----------------------------------------------------------------------" +
						"\nWelcome to KSR REAL ESTATE "+ name[location-1] +"...!"
						+"\nThere are "+ available[location-1] +" properties available to buy in and around "+ name[location-1] +"...!"
						+"\nTo buy, sell or rent property contact "+ incharge[location-1] +" : "+ contact[location-1] +
						"\n----------------------------------------------------------------------");
						if(location==1) {
							printCh();
						} else if (location==2) {
							printCo();
						} else if (location==3) {
							printTr();
						} else if (location==4) {
							printMa();
						}
			} else { System.out.println("Enter a Valid Choice...!"); }
		}
		else {
			System.out.println("Enter a Valid Location...!");
		}
	}
}

class Main{
	
  public static void main(String A[]){

    Scanner sc = new Scanner(System.in);
    Location loc = new Location();
    String adminPassword[] = {"Chennai", "Coimbatore", "Trichy","Madurai"};
    char repeat = 'y';
    while(repeat == 'y') {
    	System.out.println("------------------------- KSR REAL ESTATES ---------------------------");
        System.out.println("Enter the Location your searching for ...?\n"
        		+ "The Available Locations are...\n"
        		+ "1. Chennai\n"
        		+ "2. Coimabtore\n"
        		+ "3. Trichy\n"
        		+ "4. Madurai\n"
        		+ "----------------------------------------------------------------------");
        int location = sc.nextInt();
        loc.initialize();
        loc.getlocation(location);
        loc.putPassword(adminPassword);
        loc.execute();
        System.out.println("\n----------------------------------------------------------------------" +
        		"\n Do you Want to search for another location (y/n) ..?");
        repeat = sc.next().charAt(0);
    }
    sc.close();
  }
}