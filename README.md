👋 Hi, I'm Vincent and I love to practice my coding skills while creating different projects that primarily uses C#, HTML-CSS, JS and ASP.NET

Favorite Quote: "I want mommy's segs! AUEGH".

My favorite season is HALLOWEEN btw

👀 I’m currently interested in developing Webpages using HTML-CSS, JS, ASP.NET(RazorPages) and SQL

🌱 I’m also currently learning about Advanced Web-development,and Data Architecture.

⚡ Fun fact: I love playing racing games like Forza Horizon, Need for Speed and Initial D

Add me on my Microsoft Xbox Account: Addmerawr
  
Here are my contact details:
(TAKE NOTE: I AM VERY ACTIVE WITH THE PROVIDED SOCIAL ACCOUNT LINKS)

FB: 
https://www.facebook.com/raulvincent.rodriguez

LinkedIn:
https://www.linkedin.com/in/raul-vincent-rodriguez-3a907b286/

Gmail:
raulvincentrodriguez45626@gmail.com 

I hope we can get along well.

https://github.com/dotnet/AspNetCore.Docs/tree/8e5384ee584ac204a3a776afa6006d0a821fe438/aspnetcore

https://www.phind.com/agent?cache=cloxqbl340000ic08c6x34tuh


<!--PhindD guide for Datsys act
Certainly! Here's a basic code structure to help you get started with implementing the registration functionality in the Windows Form App:

```csharp
using System;
using System.Data.SqlClient;
using System.Windows.Forms;

namespace StudentRegistrationApp
{
    public partial class RegistrationForm : Form
    {
        private const string connectionString = "Your_Connection_String";

        public RegistrationForm()
        {
            InitializeComponent();
        }

        private void btnRegister_Click(object sender, EventArgs e)
        {
            // Retrieve input values from the form
            string firstName = txtFirstName.Text;
            string lastName = txtLastName.Text;
            int age = Convert.ToInt32(txtAge.Text);
            string email = txtEmail.Text;
            string contactNumber = txtContactNumber.Text;
            string course = txtCourse.Text;
            string password = txtPassword.Text;

            // Validate input data
            if (string.IsNullOrEmpty(firstName) || string.IsNullOrEmpty(lastName) || string.IsNullOrEmpty(email) || string.IsNullOrEmpty(password))
            {
                MessageBox.Show("Please fill in all required fields.");
                return;
            }

            // Create a new SqlConnection object
            using (SqlConnection connection = new SqlConnection(connectionString))
            {
                try
                {
                    // Open the database connection
                    connection.Open();

                    // Insert student information into the Students table
                    string insertStudentQuery = "INSERT INTO Students (FirstName, LastName, Age, Email, ContactNumber, Course) " +
                                                "VALUES (@FirstName, @LastName, @Age, @Email, @ContactNumber, @Course); " +
                                                "SELECT SCOPE_IDENTITY();";

                    SqlCommand insertStudentCommand = new SqlCommand(insertStudentQuery, connection);
                    insertStudentCommand.Parameters.AddWithValue("@FirstName", firstName);
                    insertStudentCommand.Parameters.AddWithValue("@LastName", lastName);
                    insertStudentCommand.Parameters.AddWithValue("@Age", age);
                    insertStudentCommand.Parameters.AddWithValue("@Email", email);
                    insertStudentCommand.Parameters.AddWithValue("@ContactNumber", contactNumber);
                    insertStudentCommand.Parameters.AddWithValue("@Course", course);

                    // Execute the insert query and retrieve the generated StudentID
                    int studentID = Convert.ToInt32(insertStudentCommand.ExecuteScalar());

                    // Insert login credentials into the LoginCredentials table
                    string insertLoginQuery = "INSERT INTO LoginCredentials (StudentID, Email, Password) " +
                                                "VALUES (@StudentID, @Email, @Password);";

                    SqlCommand insertLoginCommand = new SqlCommand(insertLoginQuery, connection);
                    insertLoginCommand.Parameters.AddWithValue("@StudentID", studentID);
                    insertLoginCommand.Parameters.AddWithValue("@Email", email);
                    insertLoginCommand.Parameters.AddWithValue("@Password", password);

                    // Execute the insert query for login credentials
                    insertLoginCommand.ExecuteNonQuery();

                    // Display success message and clear input fields
                    MessageBox.Show("Registration successful!");
                    ClearInputFields();
                }
                catch (Exception ex)
                {
                    MessageBox.Show("An error occurred: " + ex.Message);
                }
                finally
                {
                    // Close the database connection
                    connection.Close();
                }
            }
        }

        private void ClearInputFields()
        {
            txtFirstName.Text = "";
            txtLastName.Text = "";
            txtAge.Text = "";
            txtEmail.Text = "";
            txtContactNumber.Text = "";
            txtCourse.Text = "";
            txtPassword.Text = "";
        }
    }
}
```

This code assumes that you have a form named "RegistrationForm" with the necessary input fields and a button named "btnRegister" for the registration functionality. Replace "Your_Connection_String" with the actual connection string to your SQL Server database.

Make sure to handle any additional validation or error handling based on your specific requirements.

Let me know if you need further assistance or have any questions!


-->


<!--
**Lockheer/Lockheer** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...

-->
