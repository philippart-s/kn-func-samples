### Use Knative functions
 - create a function: `func create -l quarkus say-message -n knative-func-samples`
 - build and run the function locally: `func run -n knative-func-samples --build=false --registry=wilda`
 - test locally: `sudo env "PATH=$PATH" func invoke -n knative-func-samples` or `curl localhost:8080 -H "Content-Type:application/json" -d "{\"message\": \"👋, Hello World\"}\""`
 - create a namespace: `kubectl create ns knative-func-samples`
 - deploy the function on kuberntes: `func deploy --build=false -n knative-func-samples`
 - test remotely: `curl http://say-message.knative-func-samples.162.19.64.180.sslip.io -H "Content-Type:application/json" -d "{\"message\": \"👋, Hello World\"}\""`
 - update the function
 - update the code and redeploy it: `func deploy -n knative-func-samples`
 - remove the function: `func delete say-message -n knative-func-samples`