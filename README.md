# db2-starter
Blank definition for zOS Connect oas3 designer with Db2 placeholders.
For use with RedHat CodeReady Workspaces
Fork this project to customize and use as needed

## Structure
The `start` directory contains an initial project layout which can be used as the basis of learning the process of creating an API in the z/OS Connect Designer container. 

## Using the samples

Follow the instructions in the [IBM Documentation](https://www.ibm.com/docs/en/zosconn/zos-connect/3.0?topic=tutorials-creating-db2-zos-connect-api) on how to use this example.

## Configuration
To be able to connect to the Db2 instance in which you have the target db2 service/stored procedure installed, a file named `db2.xml` has been placed in the directory `./src/main/liberty/config`. 

The variables (e.g. `${DB2_USERNAME}`) values must be provided as environment variables when the designer image is started. The provided environment variable values will then be substituted in when the connection is used.

If you forked this repo, edit the `devfile.yaml` to update the git repository reference with your new url.

You will need to edit the `devfile.yaml` to add your credentials for accessing the database.  Replace "tsoidhere" with your tso id and "encryptedpasswordhere" with your encoded password. (Lines 29 and 31).  Instructions for encrypting the password using CodeReady Workspaces are [here](https://www.ibm.com/docs/en/SSMJPQ_api3/tutorials/encrypt_password_codeready_workspaces.html).
```
      - name: DB2_USERNAME
        value: "tsoidhere"
      - name: DB2_PASSWORD
        value: "encryptedpasswordhere"
```

Optionally, you can edit the `devfile.yaml` file to reflect the name of the API you are creating.  Replace "sample-db2-api" and "stub-db2-api" with the desired name(s).
(Lines 3, 5 and 23)
```
metadata:
  name: sample-db2-api
projects:
  - name: employees-db2-api
  .
  .
  .
 env:
   - name: ZCON_DESIGNER_PROJECT
     value: /projects/stub-db2-api/start
```

## Development
You will need to create z/OS assets for the Db2 native REST services you want to use. These z/OS assets will then need to mapped into your API. You will then need to define the responses and map each response case. The `Test` button can be used to test your API incrementally as you develop it. 

See the `Developing APIs with the z/OS Connect Designer` topic in the [IBM documentation](https://www.ibm.com/docs/en/zos-connect/zos-connect/3.0?topic=developing-apis-zos-connect-designer) for more details on using the IBM z/OS Connect Designer.  Skip the first section on downloading a designer image, as it is not applicable with this scenario.


## License

See `license.txt`
