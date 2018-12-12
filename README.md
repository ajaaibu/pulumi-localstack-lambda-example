# pulumi-localstack-lambda-example
Example project for deploying aws serverless lambda to localstack with pulumi.

### Setup

#### In the terminal run the following commands:

Install required packages 
`$ ./setup`  

Start localStack docker
`$ ./run_localstack`

### Test the application

####Deploy
Run `$ ./ deploy.sh`

output: 
``Previewing update (localstack-demo-dev):
  
       Type                             Name                                 Plan       
   +   pulumi:pulumi:Stack              localstack-demo-localstack-demo-dev  create     
   +   ├─ pulumi:providers:aws          localstack                           create     
   +   ├─ aws:iam:Role                  localstack-demo-lambda-role          create     
   +   ├─ aws:apigateway:RestApi        localstack-demo-api                  create     
   +   ├─ aws:iam:RolePolicyAttachment  localstack-demo-lambda-access        create     
   +   ├─ aws:apigateway:Resource       localstack-demo-api-resource         create     
   +   ├─ aws:lambda:Function           localstack-demo-lambda               create     
   +   ├─ aws:apigateway:Method         localstack-demo-api-method           create     
   +   ├─ aws:apigateway:Integration    localstack-demo-api-integration      create     
   +   └─ aws:apigateway:Deployment     localstack-demo-api-deployment       create     
   
  Resources:
      + 10 to create
  
  Do you want to perform this update? yes
  Updating (localstack-demo-dev):
  
       Type                             Name                                 Status      
   +   pulumi:pulumi:Stack              localstack-demo-localstack-demo-dev  created     
   +   ├─ pulumi:providers:aws          localstack                           created     
   +   ├─ aws:apigateway:RestApi        localstack-demo-api                  created     
   +   ├─ aws:iam:Role                  localstack-demo-lambda-role          created     
   +   ├─ aws:apigateway:Resource       localstack-demo-api-resource         created     
   +   ├─ aws:iam:RolePolicyAttachment  localstack-demo-lambda-access        created     
   +   ├─ aws:apigateway:Method         localstack-demo-api-method           created     
   +   ├─ aws:lambda:Function           localstack-demo-lambda               created     
   +   ├─ aws:apigateway:Integration    localstack-demo-api-integration      created     
   +   └─ aws:apigateway:Deployment     localstack-demo-api-deployment       created     
   
  Outputs:
      endpoint: "http://localhost:4567/restapis/5243580167/dev/_user_request_/mypath"
  
  Resources:
      + 10 created
  
  Duration: 15s
  
  Permalink: https://app.pulumi.com/demiban/localstack-demo-dev/updates/1
``

### Destroy

Run `$ ./destroy`

### Configuration

To change the deployment stage open `config/deploy-config.json` and change
the value of `"stage": "dev"` to `"stage": "prod" to deploy the application
the cloud.


