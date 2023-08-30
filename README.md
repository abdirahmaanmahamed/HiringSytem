
This system is Hiring with Applicant people to get company a Job. The language to build is C# and SQL server

# how to connect c# and SQL server
using System.Data.SqlClient;    
 namespace WindowsFormsApp1
{
    public partial class Login2 : Form
    {
  # created variable with connection
        SqlConnection conn;  
        public Login2()
        {
            InitializeComponent();
        }

       
 private void connect()      # This function gives connect sql and  c#
        {
            string constr = "Data Source = DESKTOP-UOO72VA\\SQLEXPRESS; Initial Catalog =HIRIG_SYSTEM;Integrated Security = SSPI";
            conn = new SqlConnection(constr);
            conn.Open();
            //conn.Close();
            //MessageBox.Show("sucessfully connection Cadde!");
        }

# login from  .I used for two texbox  . first  UserName and second Password 
namespace WindowsFormsApp1
{
    public partial class Login2 : Form
    {
        SqlConnection conn; 
        public Login2()
        {
            InitializeComponent();
        }

        private void Login2_Load(object sender, EventArgs e)
        {
            

        }


        private void button1_Click(object sender, EventArgs e)
             
        {
# I used  two variable colled datainput1 and datainput2 to store with texBox1 = username and texBox2 = password
    
            string datainput1 = textBox1.Text;
            string datainput2 = textBox2.Text;


# then if datainput1 not equal empty  and if datainput1 not equal empty


                            if (datainput1 != string.Empty)
            {
                if (datainput2 != string.Empty)
                {
                }
                try
                {
   
                    
 
# we call the functio connect 
                       connect();
                    
# the we Readed for The Database of Hiring System To Create SQL  server The Table of User_registartion to selected two Column   colled USERNAME and USERPASSWORD 

                    string xOG_Akhrin = "select * FROM User_registartion   where USERNAME='" + textBox1.Text + "' and  USERNAME='" + textBox2.Text + "'  ";


                    SqlCommand cmd = new SqlCommand(xOG_Akhrin, conn);
                    SqlDataReader rdr = cmd.ExecuteReader();
                    if (rdr.Read())
                    {
                        this.Hide();
                        home x = new home();
                        x.Show();

                    }
                    else
                    {
                        MessageBox.Show("Sorry! Data isn't Correct!! ");
                    }
                }
                catch (Exception ex)
                {
                    MessageBox.Show(ex.Message);
                }
            }
            else
            {
                MessageBox.Show("Please Enter Your personal info");
            }



        }

        private void button2_Click(object sender, EventArgs e)
        {
            textBox1.Text = string.Empty;
            textBox2.Text = string.Empty;


        }

        private void linkLabel3_LinkClicked(object sender, LinkLabelLinkClickedEventArgs e)
        {
            this.Hide();
            Forgetpassword h = new Forgetpassword();
            h.Show();
        }
       
        private void button3_Click(object sender, EventArgs e)
        {

            connect();
        }
        private void connect()
        {
            string constr = "Data Source = DESKTOP-UOO72VA\\SQLEXPRESS; Initial Catalog =HIRIG_SYSTEM;Integrated Security = SSPI";
            conn = new SqlConnection(constr);
            conn.Open();
            //conn.Close();
            //MessageBox.Show("sucessfully connection Cadde!");
        }

       
       
    }
    }




