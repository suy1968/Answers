From the data given in the excel sheet, I could infer some patterns in the usage of data -

There are many missing timestaps which indicate that the machine had been ideal at those points. The timestaps present in the data where actual computations are being performed are following some pattern and are at some irregular intervals. From the data provided to me, I could infer that we can provision the machine for 2 hours in an interval of 4 hours as each timestamp occurs in some interval of 2 hours. So lets say we provisioned the machine from 12 am to 2 am then we keep it unprovisioned from 2 am to 4 am and then continue in this pattern, hence saving cost in the process.

The next thing that I noticed in the pattern is that there are timestaps where the machine is highly overutilised for instance at 6:26:35 PM, the computation capcity being used is equal to 13760 which is way beyond 4000 and at time it is under utilised for instance at 11:52:56 PM, the computation capacity being used is equal to 5 which is way beyond the provisioned load. As, both these scnearios are bad for us we need to find a way to keep the machine utilisation roughly at X at all times.

Let us assume for now that the cost of having the provisioned load for an assigned time X is equal to C<sub>x</sub> * t where t is the number of seconds it is being provisioned for and C<sub>x</sub> is the cost of haing the provisioned load equal to X. Then we go on to calulate overutilistation as equal to Y by summing up all the instances and by how much they are over utilised, lets us assume C<sub>o</sub> is the cost for each unit of computation we use extra in this process then our total cost comes out to be equal to -

Total Cost = C<sub>x</sub> * t + C<sub>o</sub> * Y
      
We need to minise this cost but as we have not been given any data about the costs so I cannot write any procedure to solve this, rather by looking at the data and assuming both costs to be rougly equivalent, mean of the timestamps could be a great measure to minimise this cost.
On computing the mean of all the timestamps I get a value of about 3780 which is very near to 4000 and hence I feel the current load that we have provisioned for is pretty ideal in the matter. Utilising the above mentioned technique to unprovision the machine for some time could be benficial in cost cutting.

I am also attaching some visual data that I plotted to understand the usage patterns and other patterns in the data sheet provided -

![Screenshot (99)](https://user-images.githubusercontent.com/72243026/148914845-50b33e14-528c-4717-b72e-f86d0912a2b0.png)
