# Load Java class file using Jpype (combinatorial OT)

This repository contains a demo showing how to use Jpype to import Java classes. Here the java code is the implementation of a combinatorial optimal transport algorithm: https://github.com/nathaniellahn/CombinatorialOptimalTransport

## Preparation

1. To import java classes in python, we need to use Jpype. Install Jpype in conda:

```bash
conda install -c conda-forge jpype1
```

2. Under path './GTTransport/src/' create .jar file using terminal. Here we use the java class files under folder 'optimaltransport_flow_snapshot' 

```bash
jar cvf optimaltransport.jar optimaltransport
```

3. Open and run demo.ipynb

Next, we show the summary of java class Mapping, which is the main class of our OT algorithm implementation.

## **Constructor**

```java
Mapping(int n, double[] supplies, double[] demands, double[][] C, double delta)
```

Construct and execute combinatorial optimal transport algorithm

## Methods

| Return Type | Method Name         | Description                                                                                                                  |
|-------------|---------------------|------------------------------------------------------------------------------------------------------------------------------|
| double[][]  | getFlow()           | Get the final flow (100% transportation)                                                                                     |
| double      | getTotalCost()      | Get the total cost of OT  (summation of cost times flow for every edges)                                                     |
| double[]    | getDual()           | Get dual weights from every nodes                                                                                            |
| double[][]  | getFlowLog(int idx) | Get the flow logged at intermediate step, which are 25, 50, 75, 95, 98%.  Input is the index corresponding to the stop step. |
