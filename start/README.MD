# db2-starter
Blank definition for zOS Connect oas3 designer with Db2 placeholders.

## Using the samples

Follow the instructions in the [IBM Documentation](https://www.ibm.com/docs/en/zosconn/zos-connect/3.0?topic=tutorials-creating-db2-zos-connect-api) on how to use this example.

## Configuration
For directions on how to edit the devfile.yaml to reflect a specific API naming and access credentials, please refer to the README.MD file in the main branch of the git repository.

This Workspace provides a blank environment for use with a Db2 use case.  No swagger/yaml file is provided.

## Development
To reach the Browser-based Designer, click the cube on the right side of the Workspace.  Then under zosconnect, click zosconnect-ui-endpoint.  The Designer should open in a new tab.

You will need to create z/OS assets for the Db2 native REST services you want to use. These z/OS assets will then need to mapped into your API. You will then need to define the responses and map each response case. The `Test` button can be used to test your API incrementally as you develop it. 

See the `Create your first z/OS Connect API` topic in the IBM documentation for more details on using the IBM z/OS Connect Designer.


## License

See `license.txt`
