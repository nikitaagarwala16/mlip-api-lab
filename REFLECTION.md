## How to test it 
- Run ``` python3 app.py ```
- Then next try command curl -X GET -H 'Content-Type: application/json' -d '{"uri": "http://jeroen.github.io/images/testocr.png"}' http://localhost:3000/api/v1/analysis/
- Also alternatively you can try  curl -X GET -H 'Content-Type: application/json' -d '{"uri": "https://i.ibb.co/pjHgygr/IMG-4139.jpg"}' http://localhost:3000/api/v1/analysis/


## Overall what was the process
- Go to Microsoft Azure portal and create a key vault and name it
- Now you will have to add secrets to it.
- Before adding secrets go to Access Control for the vault and make sure you give Key Vault Administrator to yourself.
- Once you have added secrets you can access them.
- Please note we are using DefaultAzureCredential() it will automatically use you Azure login credentials which you have logged in via Azure CLI, you have to install azure cli as per https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-macos and follow the docs from here.

## Why not harcode credentials in code 
- Apart from all other obvious reasons do not hardcode credentials in code because if the code is in production then everytime the key changes, you will have to release this small change through a patch version which is unnecessary.
- If someone gets access to the keys then they can be misuse and add to your bill.
- When rotating credentials, if someone misses one of the locations where a set of credentials is manually entered, it can take down a mission critical service. 


