# Key Issues in doing Distributed Processing
## Think about Data Training
* If we go on to add more workers (nodes) and dsitribute the data to train the model parallely:
    * What if 1 node completes the processing before other node ?
    * What to do in case of conflict when 2 nodes complete processing at the same time and want to update model parameters or gradients simultaneously ?

## Think about Inferencing
* If we are getting more requests then does adding more servers and distributing requests equally/proportionally a correct way ?
* Are there any better load balancing strategies ?
* How to make sure that we are not processing duplicate requests on different servers ?
