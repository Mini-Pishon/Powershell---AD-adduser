# Active Directory User Management

This PowerShell script allows you to import users from a CSV file and create them in Active Directory (AD). It also checks if the user already exists before proceeding with their creation.

## Prerequisites

- PowerShell 5.1 or higher
- Active Directory module installed
- Necessary permissions to create users in AD

## CSV File

The script expects a CSV file located at the following path: `C:\AD_users.csv`. The file should be formatted with the following columns, separated by a semicolon (`;`):

FirstName;LastName
Alice;Dupont
Bob;Martin

Feel free to customize as needed.

## Usage

1. **Import the required modules:** Make sure the Active Directory module is imported by executing the following command:
    ```powershell
    Import-Module ActiveDirectory
    ```

2. **Run the script:** Execute the script in PowerShell. It will perform the following actions:
   - Check if the "Technicians" OU exists and create it if it does not.
   - Import users from the CSV file.
   - Check if each user already exists in AD before creating them.

## Example User Creation

The script also includes an example array of users to add to the "Technicians" OU. You can customize these users as needed.

```powershell
$Users = @(
    @{
        FirstName = "Alice"
        LastName = "Dupont"
        Login = "a.dupont"
        Email = "a.dupont@M2M.lan"
        Password = "Azerty1234$"
    },
    @{
        FirstName = "Bob"
        LastName = "Martin"
        Login = "b.martin"
        Email = "b.martin@M2M.lan"
        Password = "Azerty1234$"
    }
)

## Warnings
Default passwords are set in the script. It is recommended to change them to comply with your organization's security policies.
Ensure you have the necessary rights to execute this script and create users in Active Directory.
Contributing
Contributions are welcome. Feel free to submit pull requests or report issues.
