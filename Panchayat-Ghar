/*
 * Program for maintaining a student records database using File Handling.
 */

import java.io.*;
class studentRecords
{
    static BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    public void addRecords() throws IOException
    {
        System.out.print("\f");
        // Create or Modify a file for Database
        PrintWriter pw = new PrintWriter(new BufferedWriter(new FileWriter("studentRecords.dbf",true)));
        String name, Class, schNo, fname, mname, address, dob, Subjects="";
        int age;
        long telephoneNo;
        String s;
        boolean addMore = false;
        // Read Data
        do
        {
            System.out.print("\nEnter name: ");
            name = br.readLine();
            System.out.print("Father's Name: ");
            fname = br.readLine();
            System.out.print("Mother's Name: ");
            mname = br.readLine();
            System.out.print("Address: ");
            address = br.readLine();
            System.out.print("Class: ");
            Class = br.readLine();
            System.out.print("School Number: ");
            schNo = br.readLine();
            System.out.print("Enter number of subjects: ");
            int n=Integer.parseInt(br.readLine());
            String Sub[];
            Sub = new String[n];
            for(int i=0; i<n;i++)
            {
                System.out.print("Enter Subject "+(i+1)+": ");
                Sub[i]=br.readLine();
            }
            for(int i=0; i<n; i++)
            {
                Subjects+=Sub[i]+" ";
            }
            System.out.print("Date of Birth (dd/mm/yy): ");
            dob = br.readLine();
            System.out.print("Age: ");
            age = Integer.parseInt(br.readLine());
            System.out.print("Telephone No.: ");
            telephoneNo = Long.parseLong(br.readLine());
            // Print to File
            pw.println(name);
            pw.println(fname);
            pw.println(mname);
            pw.println(address);
            pw.println(Class);
            pw.println(schNo);
            pw.println(Subjects);
            pw.println(dob);
            pw.println(age);
            pw.println(telephoneNo);
            Subjects="";
            System.out.print("\nRecords added successfully !\n\nDo you want to add more records ? (y/n) : ");
            s = br.readLine();
            if(s.equalsIgnoreCase("y"))
            {
                addMore = true;
                System.out.println();
            }
            else
                addMore = false;
        }
        while(addMore);
        pw.close();
        showMenu();
    }

    public void readRecords() throws IOException
    {
        System.out.print("\f");
        try
        {
            // Open the file
            BufferedReader file = new BufferedReader(new FileReader("studentRecords.dbf"));
            String name;
            int i=1;
            // Read records from the file
            while((name = file.readLine()) != null)
            {
                System.out.println("S.No.: " +(i++));
                System.out.println("-------------");
                System.out.println("\nName : " +name);
                System.out.println("Father's Name : "+file.readLine());
                System.out.println("Mother's Name : "+file.readLine());
                System.out.println("Address : "+file.readLine());
                System.out.println("Class : "+file.readLine());
                System.out.println("School Number : "+file.readLine());
                System.out.println("Subjects : "+file.readLine());
                System.out.println("Date of Birth : "+file.readLine());
                System.out.println("Age : "+Integer.parseInt(file.readLine()));
                System.out.println("Tel. No. : "+Long.parseLong(file.readLine()));
                System.out.println();
                br.readLine();
            }
            file.close();
            showMenu();
        }
        catch(FileNotFoundException e)
        {
            System.out.println("\nERROR : File not Found !!!");
            br.readLine();
        }
    }

    public void clear() throws IOException
    {
        System.out.print("\f");
        // Create a blank file
        PrintWriter pw = new PrintWriter(new BufferedWriter(new FileWriter("studentRecords.dbf")));
        pw.close();
        System.out.println("\nAll Records cleared successfully !");
        br.readLine();
        showMenu();
    }

    public void showMenu() throws IOException
    {
        System.out.print("\f");
        System.out.println("Welcome to the Panchayat Ghar Student Management Software: Teacher Module");
        System.out.println("Please select your course of action: ");
        System.out.print("\t1 : Add Records\n\t2 : Display Records\n\t3 : Search\n\t4 : Modify\n\t5 : Delete Specific Data\n\t6 : Clear All Records\n\t7 : Exit\n\nYour Choice : ");
        int choice = Integer.parseInt(br.readLine());
        switch(choice)
        {
            case 1:
            addRecords();
            break;
            case 2:
            readRecords();
            break;
            case 3:
            Search();
            break;
            case 4: 
            modify(); 
            break;
            case 5: 
            Delete(); 
            break;
            case 6:
            clear();
            break;
            case 7:
            System.out.print("\f");
            System.out.println("Thank You for using this module");
            System.out.println("Program By:\t\tRitvik Kar\n\t\t\tThe Doon School\n\t\t\tDehradun\n\nFaculty Advisor:\tMr Vishal Mohla\nClient:\t\t\tMrs Amrit Burrett\n\nPanchayar Ghar Â® 2014-15\t\tIBDP 2015");
            break;
            default:
            System.out.println("\nInvalid Choice !");
            break;
        }
    }

    public static void start()throws IOException
    {
        studentRecords call = new studentRecords();
        System.out.println("\n\n\n\n\n\t\t\t            +-+ +-+ +-+ +-+ +-+ +-+ +-+   +-+ +-+");
        System.out.println("\t\t\t            |W| |e| |l| |c| |o| |m| |e|   |t| |o|");
        System.out.println("\t\t\t+-+ +-+ +-+ +-+-+-+-+-+-+-+-+ +-+ +-+ +-+ +-+ +-+   +-+ +-+ +-+ +-+");
        System.out.println("\t\t\t|T| |h| |e|   |P| |a| |n| |c| |h| |a| |y| |a| |t|   |G| |h| |a| |r|");
        System.out.println("\t\t\t+-+ +-+ +-+   +-+ +-+ +-+ +-+ +-+ +-+ +-+ +-+ +-+   +-+ +-+ +-+ +-+");
        br.readLine();
        call.showMenu();
    }

    public void main() throws IOException
    {
        studentRecords call = new studentRecords();
        call.showMenu();
    }

    void Search()throws IOException
    {
        System.out.print("\f");
        BufferedReader br= new BufferedReader(new InputStreamReader(System.in));
        BufferedReader ifile = new BufferedReader(new FileReader("studentRecords.dbf"));
        String name, S;
        String schNo, fname, mname, address, dob, Class, Subjects;
        int age; long telephoneNo;
        System.out.println("Enter name to be searched");
        S=br.readLine();
        boolean flag=true;
        System.out.println();
        System.out.println("---------------------------------------------------------------------------------------");
        while(true)
        {
            name=ifile.readLine();
            if(name==null)
                break;
            fname=ifile.readLine();
            mname=ifile.readLine();
            address=ifile.readLine();
            Class=ifile.readLine();
            schNo=ifile.readLine();
            Subjects=ifile.readLine();
            dob=ifile.readLine();
            age=Integer.parseInt(ifile.readLine());
            telephoneNo=Long.parseLong(ifile.readLine());
            if(S.equals(name))
            {
                System.out.println("Name : "+name+"\nFathers Name : "+fname+"\tMothers Name : "+mname+"\nAddress : "+address+"\nClass : "+Class+"\tSchool Number : "+schNo+"\nSubjects : "+Subjects+"\tDate of Birth : "+dob+"\nAge : "+age+"\tTelephone Number : "+telephoneNo);
                flag=true;
                br.readLine();
            }
        }
        if(!flag)
        {
            System.out.println("Name not found");
            br.readLine();
        }

        ifile.close();
        showMenu();
    }

    void modify()throws IOException
    {
                System.out.print("\f");
        BufferedReader br= new BufferedReader(new InputStreamReader(System.in));
        BufferedReader ifile = new BufferedReader(new FileReader("studentRecords.dbf"));
        FileWriter file= new FileWriter("temp");
        PrintWriter ofile= new PrintWriter(file);
        String name, S;
        String schNo, fname, mname, address, dob, Class, Subjects="";
        int age; long telephoneNo;
        System.out.print("Enter name to be modified: ");
        S=br.readLine();
        boolean flag=false;
        while(true)
        {
            name=ifile.readLine();
            if(name==null)
                break;
            fname=ifile.readLine();
            mname=ifile.readLine();
            address=ifile.readLine();
            Class=ifile.readLine();
            schNo=ifile.readLine();
            Subjects=ifile.readLine();
            dob=ifile.readLine();
            age=Integer.parseInt(ifile.readLine());
            telephoneNo=Long.parseLong(ifile.readLine());
            if(S.equals(name))
            {
                System.out.print("\nEnter name: ");
                name = br.readLine();
                System.out.print("Father's Name: ");
                fname = br.readLine();
                System.out.print("Mother's Name: ");
                mname = br.readLine();
                System.out.print("Address: ");
                address = br.readLine();
                System.out.print("Class: ");
                Class = br.readLine();
                System.out.print("School Number: ");
                schNo = br.readLine();
                System.out.print("Enter number of subjects: ");
                int n=Integer.parseInt(br.readLine());
                String Sub[];
                Sub = new String[n];
                for(int i=0; i<n;i++)
                {
                    System.out.print("Enter Subject "+(i+1)+": ");
                    Sub[i]=br.readLine();
                }
                Subjects="";
                for(int i=0; i<n; i++)
                {
                    Subjects+=Sub[i]+" ";
                }
                System.out.print("Date of Birth (dd/mm/yy): ");
                dob = br.readLine();
                System.out.print("Age: ");
                age = Integer.parseInt(br.readLine());
                System.out.print("Telephone No.: ");
                telephoneNo = Long.parseLong(br.readLine());
                flag=true;
            }
            ofile.println(name);
            ofile.println(fname);
            ofile.println(mname);
            ofile.println(address);
            ofile.println(Class);
            ofile.println(schNo);
            ofile.println(Subjects);
            ofile.println(dob);
            ofile.println(age);
            ofile.println(telephoneNo);
        }

        if(!flag)
            System.out.println("Name not found");
        else
            System.out.println("Data modified");

        ifile.close();
        ofile.close();
        /* Close the 2 files, The 2 files contain original and modified data respectively*/
        br.readLine();
        replace("temp","studentRecords.dbf"); /*rename the temp file to original file*/
        showMenu();
    }

    void replace(String Temp, String Ori)throws IOException
    {
        BufferedReader ifile = new BufferedReader(new FileReader(Temp));
        FileWriter file= new FileWriter(Ori);
        PrintWriter ofile= new PrintWriter(file);
        String S;
        while(true)
        {
            S=ifile.readLine();
            if(S==null)
                break;
            ofile.println(S);
        }
        ifile.close();
        ofile.close();
    }

    void Delete() throws IOException
    {
        System.out.print("\f");
        BufferedReader br= new BufferedReader(new InputStreamReader(System.in));
        BufferedReader ifile = new BufferedReader(new FileReader("studentRecords.dbf"));
        FileWriter file= new FileWriter("temp");
        PrintWriter ofile= new PrintWriter(file);
        String name, S;
        String schNo, fname, mname, address, dob, Class, Subjects;
        int age; long telephoneNo;
        System.out.print("Enter name to be deleted : ");
        S=br.readLine();
        boolean flag=false;
        while(true)
        {
            name=ifile.readLine();
            if(name==null)
                break;
            fname=ifile.readLine();
            mname=ifile.readLine();
            address=ifile.readLine();
            Class=ifile.readLine();
            schNo=ifile.readLine();
            Subjects=ifile.readLine();
            dob=ifile.readLine();
            age=Integer.parseInt(ifile.readLine());
            telephoneNo=Long.parseLong(ifile.readLine());
            if(!S.equals(name))
            {
                ofile.println(name);
                ofile.println(fname);
                ofile.println(mname);
                ofile.println(address);
                ofile.println(Class);
                ofile.println(schNo);
                ofile.println(Subjects);
                ofile.println(dob);
                ofile.println(age);
                ofile.println(telephoneNo);
            }
            else flag=true;
        }

        if(!flag)
            System.out.println("Name not found");

        ifile.close();
        ofile.close();
        /*
        Same Logic as that of modify
         */
        replace("temp","studentRecords.dbf");
        System.out.println("Data Deleted!");
        br.readLine();
        showMenu();
    }
}

/*
 * var x = 1
 * var y = 2
 * var z = "Ritvik"
 * Student newStudent = new Student(x, y, z);
 */
