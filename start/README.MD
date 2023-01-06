# db2-starter
Blank definition for zOS Connect oas3 designer with Db2 placeholders.

## Structure
The `start` directory contains an initial project layout which can be used as the basis of learning the process of creating an API in the z/OS Connect Designer container. 

## Using the samples

Follow the instructions in the [IBM Documentation](https://www.ibm.com/docs/en/zosconn/zos-connect/3.0?topic=tutorials-creating-db2-zos-connect-api) on how to use this example.

## Configuration
To be able to connect to the Db2 instance in which you have the target db2 service/stored procedure installed, a file named `db2.xml` has been placed in the directory `./src/main/liberty/config`. 

The variables (e.g. `${DB2_USERNAME}`) values must be provided as environment variables when the designer image is started. The provided environment variable values will then be substituted in when the connection is used.

You will need to edit the `devfile.yaml` to add your credentials for accessing the database.  Replace "tsoidhere" with your tso id and "passwordhere" with your password. (Lines 29 and 31)
```
      - name: DB2_USERNAME
        value: "tsoidhere"
      - name: DB2_PASSWORD
        value: "{aes}AHI+IHxZd166YhTjal48dUV9d8YISXQNj7dIcQhyS93e"
```

Optionally, you can edit the `devfile.yaml` file to reflect the name of the API you are creating.  Replace "sample-db2-api" and "stub-db2-api" with the desired name(s).
(Lines 3, 5 and 23)
```
metadata:
  name: sample-db2-api
projects:
  - name: stub-db2-api
  .
  .
  .
 env:
   - name: ZCON_DESIGNER_PROJECT
     value: /projects/stub-db2-api/start
```

## Development
You will need to create z/OS assets for the Db2 native REST services you want to use. These z/OS assets will then need to mapped into your API. You will then need to define the responses and map each response case. The `Test` button can be used to test your API incrementally as you develop it. 

See the `Create your first z/OS Connect API` topic in the IBM documentation for more details on using the IBM z/OS Connect Designer.


## License

See `license.txt`
