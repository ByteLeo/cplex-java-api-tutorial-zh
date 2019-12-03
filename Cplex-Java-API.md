**Cplex Java API**

**Contents**

<!-- MarkdownTOC -->

- [1 Cplex Java API�İ�װ������](#1-cplex-java-api�İ�װ������)
- [2 Cplex��ģ](#2-cplex��ģ)
    - [2.1 ����ӿ�](#21-����ӿ�)
    - [2.2 ���� Variables](#22-����-variables)
        - [2.2.1 ���](#221-���)
        - [2.2.2 ���ú���](#222-���ú���)
        - [2.2.3 ������ʽ���](#223-������ʽ���)
    - [2.3 ���ʽ Expressions](#23-���ʽ-expressions)
        - [2.3.1 ���](#231-���)
        - [2.3.2 ���� IloLinearNumExpr ���ú���](#232-����-ilolinearnumexpr-���ú���)
    - [2.4 Լ�� Ranged constraints](#24-Լ��-ranged-constraints)
        - [2.4.1 ���Լ��](#241-���Լ��)
            - [2.4.1.1 lb <= expr <= ub](#2411-lb--expr--ub)
            - [2.4.1.2 expr <= ub](#2412-expr--ub)
            - [2.4.1.3 expr >= lb](#2413-expr--lb)
        - [2.4.2 IloRange�ĳ��ú���](#242-ilorange�ĳ��ú���)
    - [2.5 Ŀ�꺯�� Objective function](#25-Ŀ�꺯��-objective-function)
        - [2.5.1 ���ú���](#251-���ú���)
    - [2.6 ��ģ��ʽ](#26-��ģ��ʽ)
        - [2.6.1 ���н�ģpopulateByRow](#261-���н�ģpopulatebyrow)
        - [2.6.2 ���н�ģpopulateByColumn](#262-���н�ģpopulatebycolumn)
            - [2.6.2.1 ����](#2621-����)
            - [2.6.2.2 ����ʾ��](#2622-����ʾ��)
        - [2.6.3 �����㽨ģpopulateByNonzero�������ã�](#263-�����㽨ģpopulatebynonzero�������ã�)
    - [2.7 ģ�����](#27-ģ�����)
    - [2.8 ��ȡ�����Ϣ](#28-��ȡ�����Ϣ)
        - [2.8.1 Ŀ�꺯��](#281-Ŀ�꺯��)
        - [2.8.2 ����](#282-����)
        - [2.8.3 Լ��](#283-Լ��)
            - [2.8.3.1 �ɳڱ���](#2831-�ɳڱ���)
            - [2.8.3.2 ��ż����](#2832-��ż����)
        - [2.8.4 ������](#284-������)
    - [2.9 ģ�͵����뵼��](#29-ģ�͵����뵼��)
    - [2.10 ����](#210-����)
        - [2.10.1 �ٷ�����](#2101-�ٷ�����)
        - [2.10.2 ���ò���](#2102-���ò���)
            - [2.10.2.1 ����ʱ��](#21021-����ʱ��)
            - [2.10.2.2 Random seed](#21022-random-seed)
            - [2.10.2.3 Presolve](#21023-presolve)
            - [2.10.2.4 RootAlgorithm](#21024-rootalgorithm)
            - [2.10.2.5 Tolerance](#21025-tolerance)
            - [2.10.2.6 NodeAlgorithm](#21026-nodealgorithm)
            - [2.10.2.7 Benders Strategy](#21027-benders-strategy)
            - [2.10.2.8 Search Strategy](#21028-search-strategy)
            - [2.10.2.9 MIP ��ƽ�濪��](#21029-mip-��ƽ�濪��)
            - [2.10.2.10 MIP �ڵ�ѡ�����](#210210-mip-�ڵ�ѡ�����)
            - [2.10.2.11 MIP ��֧����](#210211-mip-��֧����)
            - [2.10.2.12 MIP ����е�Ŀ��ֵ����Gap](#210212-mip-����е�Ŀ��ֵ����gap)
            - [2.10.2.13 MIP �ڵ���������](#210213-mip-�ڵ���������)
            - [2.10.2.14 MIP ǿ������](#210214-mip-ǿ������)
            - [2.10.2.15 MIP �ڵ���־��ʾ��Ϣ](#210215-mip-�ڵ���־��ʾ��Ϣ)
            - [2.10.2.16 ������Ϣ��ʾ](#210216-������Ϣ��ʾ)
            - [2.10.2.17 �����η���Ϣ��ʾ](#210217-�����η���Ϣ��ʾ)
            - [2.10.2.18 MIP �ڵ���־���](#210218-mip-�ڵ���־���)
            - [2.10.2.19 MIP heuristic frequency](#210219-mip-heuristic-frequency)
    - [2.11 ����](#211-����)
        - [2.11.1 �߼�Լ��](#2111-�߼�Լ��)
- [3 Legacy Callback](#3-legacy-callback)
    - [3.1 �ο��ص�Informational callback](#31-�ο��ص�informational-callback)
        - [3.1.1 ���](#311-���)
        - [3.1.2 �漰����](#312-�漰����)
        - [3.1.3 ʾ���ļ�MIPex4.java](#313-ʾ���ļ�mipex4java)
            - [3.1.3.1 ����һ���������ʱ���gap���Ƴ����Ƿ���ֹ](#3131-����һ���������ʱ���gap���Ƴ����Ƿ���ֹ)
            - [3.1.3.2 ���ܶ�����ӡ��־](#3132-���ܶ�����ӡ��־)
    - [3.2 ��ѯ����ϻص�Query or diagnostic callbacks](#32-��ѯ����ϻص�query-or-diagnostic-callbacks)
        - [3.2.1 ���](#321-���)
        - [3.2.2 ����λ��](#322-����λ��)
    - [3.3 ���ƻص�](#33-���ƻص�)
        - [3.3.1 ���](#331-���)
        - [3.3.2 ʹ�ó���](#332-ʹ�ó���)
            - [3.3.2.1 �ڵ�ص�](#3321-�ڵ�ص�)
            - [3.3.2.2 ���ص�](#3322-���ص�)
            - [3.3.2.3 �û���ƽ��ص�](#3323-�û���ƽ��ص�)
            - [3.3.2.4 ����Լ���ص�](#3324-����Լ���ص�)
            - [3.3.2.5 ̽�Իص�](#3325-̽�Իص�)
            - [3.3.2.6 ��֧�ص�](#3326-��֧�ص�)
            - [3.3.2.7 ���ν�ص�](#3327-���ν�ص�)
    - [3.4 �ص�����ֹ](#34-�ص�����ֹ)
    - [3.5 Legacy Callbackʾ��](#35-legacy-callbackʾ��)
        - [3.5.1 AdMIPex1: node and branch callbacks](#351-admipex1-node-and-branch-callbacks)
            - [3.5.1.1 branch callbacks](#3511-branch-callbacks)
            - [3.5.1.2 node callbacks](#3512-node-callbacks)
        - [3.5.2 AdMIPex3: Special Ordered Sets Type 1](#352-admipex3-special-ordered-sets-type-1)
        - [3.5.3 AdMIPex2: HeuristicCallback](#353-admipex2-heuristiccallback)
        - [3.5.4 AdMIPex4: UserCutCallback and LazyConstraintCallback](#354-admipex4-usercutcallback-and-lazyconstraintcallback)
        - [3.5.5 AdMIPex5: UserCutCallback and LazyConstraintCallback](#355-admipex5-usercutcallback-and-lazyconstraintcallback)
            - [3.5.5.1 UserCutCallback](#3551-usercutcallback)
            - [3.5.5.2 UserCutCallback](#3552-usercutcallback)
            - [3.5.5.3 LazyConstraintCallback](#3553-lazyconstraintcallback)
        - [3.5.6 AdMIPex6: SolveCallback��passing in a solution for the root node](#356-admipex6-solvecallback��passing-in-a-solution-for-the-root-node)
- [4 Generic Callback](#4-generic-callback)
    - [4.1 ���](#41-���)
    - [4.2 ����](#42-����)
    - [4.3 ͨ�ûص���������Context](#43-ͨ�ûص���������context)
        - [4.3.1 IloCplex.Callback.Context.Id�е������ĳ���](#431-ilocplexcallbackcontextid�е������ĳ���)
            - [4.3.1.1 ThreadUp](#4311-threadup)
            - [4.3.1.2 ThreadDown](#4312-threaddown)
            - [4.3.1.3 LocalProgress](#4313-localprogress)
            - [4.3.1.4 GlobalProgress](#4314-globalprogress)
            - [4.3.1.5 Candidate](#4315-candidate)
            - [4.3.1.6 Relaxation](#4316-relaxation)
        - [4.3.2 ʹ�÷���](#432-ʹ�÷���)
    - [4.4 Generic Callbackʾ��](#44-generic-callbackʾ��)
        - [4.4.1 AdMIPex8: Cut](#441-admipex8-cut)
        - [4.4.2 AdMIPex9: HeuristicCallback](#442-admipex9-heuristiccallback)
- [5 Cplex �ٷ�ʾ��˵��](#5-cplex-�ٷ�ʾ��˵��)

<!-- /MarkdownTOC -->


<a id="1-cplex-java-api�İ�װ������"></a>
# 1 Cplex Java API�İ�װ������
1. ���ذ�װCplex������ס��װĿ¼

2. ����Cplex.jar��
    - Step 1  
    ![Import Cplex Java API 1](./pictures/java_api_setting/import_cplex_jar1.png)
    - Step 2
    ![Import Cplex Java API 2](./pictures/java_api_setting/import_cplex_jar2.png)
    - Step 3
    ![Import Cplex Java API 3](./pictures/java_api_setting/import_cplex_jar3.png)

3. Javadoc
    - ����
        + Step 1
        ![Javadoc Setting1](./pictures/java_api_setting/javadoc_setting1.png)
        + Step 2
        ![Javadoc Setting2](./pictures/java_api_setting/javadoc_setting2.png)
    - Ч��
        + ��ͣ�鿴�ࡢ���������Եȵ�˵��
        ![Javadoc1](./pictures/java_api_setting/javadoc1.png)

        + ��Eclipse��ֱ�Ӵ�javadoc�ĵ�
        + ![Javadoc2](./pictures/java_api_setting/javadoc2.png)


4. Djava.library.path
    - ����һ������JVM������<https://www.ibm.com/support/knowledgecenter/SSSA5P_12.5.0/ilog.odms.cplex.help/CPLEX/GettingStarted/topics/set_up/Eclipse.html>
    - ������������Native Library Location
        + Step 1
        ![Native Library Location1](./pictures/java_api_setting/Djava_library_path1.png)
        + Step 2
        ![Native Library Location2](./pictures/java_api_setting/Djava_library_path2.png)

5. ���
![finally](./pictures/java_api_setting/finally.png)

<a id="2-cplex��ģ"></a>
# 2 Cplex��ģ
<a id="21-����ӿ�"></a>
## 2.1 ����ӿ�
* IloCplexModeler Class
* IloModeler Interfaces
* **`IloCplex class`**
    - The class IloCplex extends IloCplexModeler
    - IloCplex implements the solving methods
    - IloCplex implements interfaces IloModeler

**һ��ʹ�� IloCplex cplex = new IloCplex() �½�ģ��**

<a id="22-����-variables"></a>
## 2.2 ���� Variables
<a id="221-���"></a>
### 2.2.1 ���
* ��������
    - 0-1������IloNumVarType.Bool
    - ���ͱ�����IloNumVarType.Int
    - ����������IloNumVarType.Float
* ����һ��ʹ�� `IloNumVar` ����

<a id="222-���ú���"></a>
### 2.2.2 ���ú���
* **`IloCplex.numVar(double lb, double ub, IloNumVarType type, String name)`**
* IloCplex.intVar(): To create integer variables
* IloCplex.boolVar(): To create 0 / 1 variables

<a id="223-������ʽ���"></a>
### 2.2.3 ������ʽ���
* numVarArray()
* intVarArray()
* boolVarArray()


<a id="23-���ʽ-expressions"></a>
## 2.3 ���ʽ Expressions
<a id="231-���"></a>
### 2.3.1 ���
* ģ�͵�Ŀ�꺯����Լ�����ڱ��ʽ���ж���
* ���� `IloNumExpr` �ӿڼ����ӽӿ�
* ����
    - IloModeler.sum
    - IloModeler.prob: ������һ�����ʽ���������볣���ĳ˻�
        + �ֿ��������ƣ�IloModeler.prod(capacity, opened[j])
    - IloModeler.scalProd: �����ڱ���������ϵ������ĵ��
        + �ֿ⿪ͨ�ɱ����㣺IloModeler.scalProd(cost[c], supply[c])
    - IloModeler.diff: ���
    - IloModeler.negative: ��-1
    - IloModeler.square
* ���õĳ���
    - �����ʽ�ɶ��`������`�����`ϵ��������ĳ˻�`��ɣ����� IloNumExpr �ӿ�
    - �����ʽ�ɶ��`ϵ���ͱ����ĳ˻�`��ɣ����� IloLinearNumExpr �ӿ�
    - IloLinearNumExpr �ӿ��ڳ�ʼ��ʱ����ָ���������֣���˶��ڵ�һ�ֳ���Ҳ����ͨ�� double ���ͽ������Ȼ���ڳ�ʼ����ʱ����Ϊ������һ������ӣ�����ʣ�µĶ��`ϵ��������ĳ˻�`��ʹ�� `addTerm`�������

<a id="232-����-ilolinearnumexpr-���ú���"></a>
### 2.3.2 ���� IloLinearNumExpr ���ú���
![Expressions���ú���](./pictures/Expressions���ú���.png)


<a id="24-Լ��-ranged-constraints"></a>
## 2.4 Լ�� Ranged constraints
* ʹ�� IloRange ����
* ��ʾ���� lb <= expression <= ub ��Լ��

<a id="241-���Լ��"></a>
### 2.4.1 ���Լ��
<a id="2411-lb--expr--ub"></a>
#### 2.4.1.1 lb <= expr <= ub
IloRange rng = cplex.range(lb, expr, ub, name);
    
    - lb and ub are double values
    - expr is of type IloNumExpr
    - name is a string

<a id="2412-expr--ub"></a>
#### 2.4.1.2 expr <= ub
* IloRange le = IloCplex.le(expr, ub, name)
* IloCplex.addLe(expr, ub, name)
* ��ȵ�һ�֣��ڶ��ֻ��Լ�����뵽��ǰģ����

<a id="2413-expr--lb"></a>
#### 2.4.1.3 expr >= lb
* IloRange ge = IloCplex.le(expr, lb, name)
* IloCplexModeler.addGe(expr, lb, name)
* ��ȵ�һ�֣��ڶ��ֻ��Լ�����뵽��ǰģ����

<a id="242-ilorange�ĳ��ú���"></a>
### 2.4.2 IloRange�ĳ��ú���
![IloRange�ĳ��ú���](./pictures/IloRange�ĳ��ú���.png)


<a id="25-Ŀ�꺯��-objective-function"></a>
## 2.5 Ŀ�꺯�� Objective function
* ʹ��IloObjective����
* ��Ҫ��
    - sense: Maximize or Minimize
    - expression: Ŀ�꺯�����ʽ
    - name: Ŀ�꺯�����ƣ���ѡ������

<a id="251-���ú���"></a>
### 2.5.1 ���ú���
* IloObjective obj = IloCplexModeler.addMaximize(expr)
* IloObjective obj = IloCplexModeler.add(cplex.maximize(expr))
* setExpr(expr): �����ڸ���Ŀ�꺯�������������е�pricing problem


<a id="26-��ģ��ʽ"></a>
## 2.6 ��ģ��ʽ

<a id="261-���н�ģpopulatebyrow"></a>
### 2.6.1 ���н�ģpopulateByRow
```
Input data:
foodMin[j]          minimum amount of food j to use
foodMax[j]          maximum amount of food j to use 
foodCost[j]         cost for one unit of food j
nutrMin[i]          minimum amount of nutrient i
nutrMax[i]          maximum amount of nutrient i
nutrPerFood[i][j]   nutrition amount of nutrient i in food j

Modeling variables:
buy[j]              amount of food j to purchase

Objective:
minimize sum(j) buy[j] * foodCost[j]

Constraints:
forall foods i: nutrMin[i] <= sum(j) buy[j] * nutrPer[i][j] <= nutrMax[j]
```

```JAVA
static void buildModelByRow(IloModeler model, Data data, IloNumVar[] buy, IloObjective cost, IloNumVarType type)
        throws IloException {
    int nFoods = data.nFoods;
    int nNutrs = data.nNutrs;

    // ��ѭ����ʽ�½�����
    for (int j = 0; j < nFoods; j++) {
        buy[j] = model.numVar(data.foodMin[j], data.foodMax[j], type);
    }

    // ����Ŀ�꺯��
    cost.setExpr(model.scalProd(data.foodCost, buy));

    // �������Լ��
    for (int i = 0; i < nNutrs; i++) {
        model.addRange(data.nutrMin[i], model.scalProd(data.nutrPerFood[i], buy), data.nutrMax[i]);
    }
}
```


<a id="262-���н�ģpopulatebycolumn"></a>
### 2.6.2 ���н�ģpopulateByColumn
������ӱ���������ӱ�������Ҫ����:

* ��Ŀ�꺯����Ӱ��
* ��Լ����Ӱ��

<a id="2621-����"></a>
#### 2.6.2.1 ����
1. ����ģ��Ϊ IloMPModeler model
2. ȡ��Ŀ�꺯�������ã����õ� IloObjective objective
3. ����Լ����lowerBound��upperBound���õ� IloRange[] constraint
4. ��ÿ������
    * ��ñ�����Ӧ��ϵ��һ����ӵ�Ŀ�꺯���У���������һ���ж���  
        - **`IloColumn col = model.column(objective, coefficient)`**
    * ��ÿ��Լ��
        - ʹ�� **`model.column(IloRange constraint[i], double val)`** Ϊ��������ڸ�Լ���е�ϵ����������һ���ж��� IloColumn col2
        - ʹ��IloColumn.and()������ col �� col2 ���С����ӡ�  
        **`col = col.and(col2)`**
        - ����˶�Ŀ�꺯���Լ�Լ���ĸ���
    * ʹ�� **`model.numVar(IloColumn col, double lb, double ub, IloNumVarType type)`** Ϊ�µ������ö�Ӧ�ı������������½硢���ͣ�


<a id="2622-����ʾ��"></a>
#### 2.6.2.2 ����ʾ��
```JAVA
static void buildModelByColumn(IloMPModeler model, Data data, IloNumVar[] buy, IloObjective cost,
        IloNumVarType type) throws IloException {
    int nFoods = data.nFoods;
    int nNutrs = data.nNutrs;

    IloRange[] constraint = new IloRange[nNutrs];

    // ����Լ����lowerBound��upperBound
    for (int i = 0; i < nNutrs; i++) {
        constraint[i] = model.addRange(data.nutrMin[i], data.nutrMax[i]);
    }

    for (int j = 0; j < nFoods; j++) {
        // ��ñ�����Ӧ��ϵ��һ����ӵ�Ŀ�꺯���У���������һ���ж���
        IloColumn col = model.column(cost, data.foodCost[j]);
        for (int i = 0; i < nNutrs; i++) {
            // Ϊ��������ڸ�Լ���е�ϵ����������һ���ж���ʹ��IloColumn.and()�����ӡ�������
            col = col.and(model.column(constraint[i], data.nutrPerFood[i][j]));
        }
        // Ϊ�µ������ö�Ӧ�ı������������½硢���ͣ�
        buy[j] = model.numVar(col, data.foodMin[j], data.foodMax[j], type);
    }
}
```

<a id="263-�����㽨ģpopulatebynonzero�������ã�"></a>
### 2.6.3 �����㽨ģpopulateByNonzero�������ã�
A Simlpe Model(Example: LPex1.java)
```
The following methods all populate the problem with data for the following
linear program:

Maximize
x1 + 2 x2 + 3 x3
Subject To
- x1 + x2 + x3 <= 20
x1 - 3 x2 + x3 <= 30
Bounds
0 <= x1 <= 40
End
```

```JAVA
static void populateByNonzero(IloMPModeler model, IloNumVar[][] var, IloRange[][] rng) throws IloException {
    double[] lb = { 0.0, 0.0, 0.0 };
    double[] ub = { 40.0, Double.MAX_VALUE, Double.MAX_VALUE };
    IloNumVar[] x = model.numVarArray(3, lb, ub);
    var[0] = x;

    double[] objvals = { 1.0, 2.0, 3.0 };
    model.add(model.maximize(model.scalProd(x, objvals)));

    rng[0] = new IloRange[2];
    rng[0][0] = model.addRange(-Double.MAX_VALUE, 20.0);
    rng[0][1] = model.addRange(-Double.MAX_VALUE, 30.0);

    rng[0][0].setExpr(model.sum(model.prod(-1.0, x[0]), model.prod(1.0, x[1]), model.prod(1.0, x[2])));
    rng[0][1].setExpr(model.sum(model.prod(1.0, x[0]), model.prod(-3.0, x[1]), model.prod(1.0, x[2])));

    x[0].setName("x1");
    x[1].setName("x2");
    x[2].setName("x3");
    rng[0][0].setName("c1");
    rng[0][1].setName("c2");
}
```


<a id="27-ģ�����"></a>
## 2.7 ģ�����
* ����IloCplex.slove()
* ������ͷ��� IloCplex.Status
    - Bounded
    - Unbounded
    - Feasible
    - Infeasible
    - InfeasibleOrUnbounded
    - Error
    - Unknown
    - Optimal
* �ɽ��[����](#210-����)���֣������ǰ�����������

<a id="28-��ȡ�����Ϣ"></a>
## 2.8 ��ȡ�����Ϣ
<a id="281-Ŀ�꺯��"></a>
### 2.8.1 Ŀ�꺯��
IloCplex.getObjValue()

<a id="282-����"></a>
### 2.8.2 ����
* ��ȡ��������ֵ double IloCplex.getValue(var)
* ��ȡ���������ֵ double[] IloCplex.getValues(vars)
* IloCplex.getReducedCost(ivar)
* IloCplex.getReducedCosts(vars)

<a id="283-Լ��"></a>
### 2.8.3 Լ��
<a id="2831-�ɳڱ���"></a>
#### 2.8.3.1 �ɳڱ���
* IloCplex.getSlack(IloRange rng)
* IloCplex.getSlacks(IloRange[] rng)
* IloCplex.getSlacks(IloLPMatrix matrix)

<a id="2832-��ż����"></a>
#### 2.8.3.2 ��ż����
* IloCplex.getDual(IloRange rng)
* IloCplex.getDuals(IloRange[] rng)
* IloCplex.getDuals(IloLPMatrix matrix)

<a id="284-������"></a>
### 2.8.4 ������
IloLinearNumExpr IloCplex.getRay()


<a id="29-ģ�͵����뵼��"></a>
## 2.9 ģ�͵����뵼��
* Exporting models  
IloCplex.exportModel(��diet.lp")

* Importing models  
IloCplex.importModel()


<a id="210-����"></a>
## 2.10 ����
<a id="2101-�ٷ�����"></a>
### 2.10.1 �ٷ�����
[Cplex�ٷ�������������](https://www.ibm.com/support/knowledgecenter/zh/SSSA5P_12.8.0/ilog.odms.cplex.help/CPLEX/Parameters/topics/introListAlpha.html)

<a id="2102-���ò���"></a>
### 2.10.2 ���ò���
<a id="21021-����ʱ��"></a>
#### 2.10.2.1 ����ʱ��
IloCplex.Param.TimeLimit

<a id="21022-random-seed"></a>
#### 2.10.2.2 Random seed
����������ӣ�IloCplex.setParam(IloCplex.Param.RandomSeed, seed);

<a id="21023-presolve"></a>
#### 2.10.2.3 Presolve
* �ر�Ԥ��⣬IloCplex.setParam(IloCplex.Param.Preprocessing.Presolve, false)
* �ر�Ԥ���������IloCplex.setParam(IloCplex.Param.Preprocessing.Reduce, 0);

<a id="21024-rootalgorithm"></a>
#### 2.10.2.4 RootAlgorithm
* ʹ�õ����η�����һ��LP���⣬IloCplex.setParam(IloCplex.Param.RootAlgorithm, IloCplex.Algorithm.Primal)��Ҳ���Ե��������㷨��
    - 0, IloCplex.Algorithm.Auto: �Զ�ѡ��
    - 1, IloCplex.Algorithm.Primal: �����η�
    - 2, IloCplex.Algorithm.Dual: ��ż�����η�
    - 3, IloCplex.Algorithm.Network: network simplex algorithm
    - 4, IloCplex.Algorithm.Barrier: barrier algorithm
    - 5, IloCplex.Algorithm.Sifting: use the sifting algorithm
    - 6, IloCplex.Algorithm.Concurrent:  use multiple algorithms concurrently on a multiprocessor system
* �ɲο�ʾ���ļ�LPex7.java

<a id="21025-tolerance"></a>
#### 2.10.2.5 Tolerance
* IloCplex.Param.Simplex.Tolerances.Optimality
    - Influences the reduced-cost tolerance for optimality
    - This parameter governs how closely CPLEX must approach the theoretically optimal solution
    - Value: Any number from 1e-9 to 1e-1; default: 1e-06
* IloCplex.Param.Simplex.Tolerances.Markowitz
    - Influences pivot selection during basis factoring
    - Increasing the Markowitz threshold may improve the numerical properties of the solution
    - Value: Any number from 0.0001 to 0.99999; default: 0.01
* IloCplex.Param.Simplex.Tolerances.Feasibility
    - Specifies the feasibility tolerance, that is, the degree to which values of the basic variables calculated by the simplex method may violate their bounds.
    - Value: Any number from 1e-9 to 1e-1; default: 1e-06.

<a id="21026-nodealgorithm"></a>
#### 2.10.2.6 NodeAlgorithm
IloCplex.Param.NodeAlgorithm����ѡ�㷨��

* 0, IloCplex.Algorithm.Auto: �Զ�ѡ��
* 1, IloCplex.Algorithm.Primal �����η�
* 2, IloCplex.Algorithm.Dual: ��ż�����η�
* 3, IloCplex.Algorithm.Network: network simplex algorithm
* 4, IloCplex.Algorithm.Barrier: barrier algorithm
* 5, IloCplex.Algorithm.Sifting: use the sifting algorithm

<a id="21027-benders-strategy"></a>
#### 2.10.2.7 Benders Strategy
IloCplex.Param.Benders.Strategy����ѡ��

* -1, IloCplex.BendersStrategy.Off
    - ִ�д�ͳ��֧�ͽ��ޣ������κ� Benders ע�ͣ�Ҳ��ʹ�� Benders �㷨

* 0, IloCplex.BendersStrategy.Auto
    - ��� 1���û�δ��ģ���ṩע��  
    CPLEX ִ�д�ͳ��ͳ���ƶ��編
    - ��� 2���û��ṩ��ע��  
    CPLEX ����ע�ͷֽ��������������⣬���ҳ����ܷ��һ���ֽ�������

* 1, IloCplex.BendersStrategy.User
    - CPLEX �ϸ����ע�ͷֽ�ģ��

* 2, IloCplex.BendersStrategy.Workers
    - CPLEX ����ע��ȷ�������⣬�����Խ�ʣ��ı����ֽ�ɲ���ص������Ⲣ������ͬ��Worker

* 3, IloCplex.BendersStrategy.Full: CPLEX�Զ��ֽ�ģ�ͣ����Կ����ṩ���κ�ע��
    - �����������������뵽������
    - �����������������뵽������
    - ��һ���ֽ�������⣨������ܣ�

**`ע�⣺����û�ע�ʹ���Cplex���׳����󣬼�ʹ Auto Ҳ������ȫ�����ܡ��ġ�`**


**Bendersע�ͷֽ�ʾ��**  
```JAVA
// Create an annotation and you can set a default value here
IloCplex.LongAnnotation benders = cplex.newLongAnnotation(IloCplex.CPX_BENDERS_ANNOTATION);

// Put the binary "use" variables in the master problem��0 represents master problem
for (IloNumVar u : use) {
    cplex.setAnnotation(benders, u, 0);
}

/*
 * The LP portion does not decompose into smaller problems,
 * so we put all the "ship" variables in subproblem 1.
 * If the LP portion can be decomposed, wen can assign 2, 3, 4... to the variable
 */
for (IloNumVar[] s : ship) {
    for (IloNumVar s0 : s) {
        cplex.setAnnotation(benders, s0, 1);
    }
}
// Set the default Benders strategy to be adherence to our design.
cplex.setParam(IloCplex.Param.Benders.Strategy,
                   IloCplex.BendersStrategy.User);
```


<a id="21028-search-strategy"></a>
#### 2.10.2.8 Search Strategy
IloCplex.Param.MIP.Strategy.Search����ѡ:

* 0, IloCplex.MIPSearch.Auto Ĭ���Զ�ѡ��
* 1, IloCplex.MIPSearch.Traditional ʹ�÷�֧�������
* 2, IloCplex.MIPSearch.Dynamic ʹ�ö�̬��������            


<a id="21029-mip-��ƽ�濪��"></a>
#### 2.10.2.9 MIP ��ƽ�濪��
1.  Gomory Cuts
    * IloCplex.Param.MIP.Cuts.Gomory

2. ����� Cliques Cuts
    * IloCplex.Param.MIP.Cuts.Cliques
    * A clique is a relationship among a group of binary variables such that at most one variable in the group can be positive in any integer feasible solution. Before optimization starts, CPLEX constructs a graph representing these relationships and finds maximal cliques in the graph.

3. ��С���� Cover Cuts
    * IloCplex.Param.MIP.Cuts.Covers
    * If a constraint takes the form of a knapsack constraint (that is, a sum of binary variables with nonnegative coefficients less than or equal to a nonnegative righthand side), then there is a minimal cover associated with the constraint. A minimal cover is a subset of the variables of the inequality such that if all the subset variables were set to one, the knapsack constraint would be violated, but if any one subset variable were excluded, the constraint would be satisfied. CPLEX can generate a constraint corresponding to this condition, and this cut is called a cover cut.

4. MIR Cuts
    * IloCplex.Param.MIP.Cuts.MIRCut
    * MIR cuts are generated by applying integer rounding on the coefficients of integer variables and the righthand side of a constraint.

5. Zero-half cuts
    * IloCplex.Param.MIP.Cuts.ZeroHalfCut
    * Zero-half cuts are based on the observation that when the lefthand side of an inequality consists of integral variables and integral coefficients, then the righthand side can be rounded down to produce a zero-half cut. 

4. Flow Cover Cuts
    * IloCplex.Param.MIP.Cuts.FlowCovers
    * Flow covers are generated from constraints that contain continuous variables, where the continuous variables have variable upper bounds that are zero or positive depending on the setting of associated binary variables. The idea of a flow cover comes from considering the constraint containing the continuous variables as defining a single node in a network where the continuous variables are in-flows and out-flows. The flows will be on or off depending on the settings of the associated binary variables for the variable upper bounds. The flows and the demand at the single node imply a knapsack constraint. That knapsack constraint is then used to generate a cover cut on the flows (that is, on the continuous variables and their variable upper bounds).

5. Flow path Cuts
    * IloCplex.Param.MIP.Cuts.PathCut
    * Flow path cuts are generated by considering a set of constraints containing the continuous variables that define a path structure in a network, where the constraints are nodes and the continuous variables are in-flows and out-flows. The flows will be on or off depending on the settings of the associated binary variables.

6. Global Implied bounds Cut
    * IloCplex.Param.MIP.Cuts.Implied
    * In some models, binary variables imply bounds on nonbinary variables (that is, general integer variables and continuous variables). CPLEX generates cuts to reflect these relationships.
    * CPLEX generates global implied bound cuts by using globally valid bounds on the continuous variables in the model. For a parameter to control this activity, see the documentation of the MIP globally valid implied bound cuts switch in the CPLEX Parameters Reference Manual.

7. Lift and project cuts
    * IloCplex.Param.MIP.Cuts.LiftProj
    * <https://www.ibm.com/support/knowledgecenter/en/SSSA5P_12.6.3/ilog.odms.cplex.help/CPLEX/UsrMan/topics/discr_optim/mip/cuts/35_liftproj.html>

<a id="210210-mip-�ڵ�ѡ�����"></a>
#### 2.10.2.10 MIP �ڵ�ѡ�����
IloCplex.Param.MIP.Strategy.NodeSelect

* 0, IloCplex.NodeSelect.DFS �����������
* 1, IloCplex.NodeSelect.BestBound ��ѱ߽�������ȱʡֵ
* 2, IloCplex.NodeSelect.BestEst ��ѹ�������
* 3, IloCplex.NodeSelect.BestEstAlt ������ѹ�������

<a id="210211-mip-��֧����"></a>
#### 2.10.2.11 MIP ��֧����
IloCplex.Param.MIP.Strategy.Branch����֧���򣬿�ѡ��

* -1, IloCplex.BranchDirection.Down
* 0, IloCplex.BranchDirection.Auto
* 1, IloCplex.BranchDirection.Up
* һ����makeBranch(IloNumVar var, double bound, **`BranchDirection dir`**, double objestimate)ʹ��

<a id="210212-mip-����е�Ŀ��ֵ����gap"></a>
#### 2.10.2.12 MIP ����е�Ŀ��ֵ����Gap
IloCplex.Param.MIP.Pool.RelGap�������ж��Ƿ����⵽�ⷨ���У����磬������˲�������Ϊ 0.01����ô�����������β� 1% �����Ľ⡣

<a id="210213-mip-�ڵ���������"></a>
#### 2.10.2.13 MIP �ڵ���������
IloCplex.Param.MIP.Limits.Nodes�������������㷨��ֹ��δ�ﵽ������֮ǰ�������ڵ�����

<a id="210214-mip-ǿ������"></a>
#### 2.10.2.14 MIP ǿ������
IloCplex.Param.Emphasis.MIP�����ڿ��� MIP ���ٶȡ������ԡ������Ժ��ƶ�����֮������ԣ���ѡ��

* 0: ��ʹ��ȱʡ���� BALANCED ʱ��CPLEX �����ڿ���֤����ѽⷨ����Ҫ�������Ż������ҵ����������нⷨ
* 1: �ڽ��˲�������Ϊ FEASIBILITY ʱ��CPLEX �����Ż�����ʱƵ�����ɸ�����еĽⷨ������һ����������֤���ٶ�
* 2: ������Ϊ OPTIMALITY ʱ�����ڽ׶�Ӧ���ڲ��ҿ��еĽⷨ�Ĺ���������
* 3: ʹ������ BESTBOUND ʱ����ͨ���ƶ���ѽ���ֵ��������ǿ��֤�������ԣ����˳������еĽⷨ������Ϊ��ΪżȻ
* 4: �ڲ�������Ϊ HIDDENFEAS ʱ��MIP �Ż�����Ŭ�����ҷǳ������ҵ��ĸ��������еĽⷨ������� FEASIBILITY ���������ҵ��ɽ��������Ľⷨʱ���Ǵ�����

<a id="210215-mip-�ڵ���־��ʾ��Ϣ"></a>
#### 2.10.2.15 MIP �ڵ���־��ʾ��Ϣ
IloCplex.Param.MIP.Display�������ڻ�������Ż� (MIP) �ڼ� CPLEX ���浽��Ļ����¼����־�е����ݣ���ѡ��

* 0: �ҵ���ѽ֮ⷨ�����ʾ
* 1: ��ʾ�������нⷨ
* 2: Ĭ��ֵ����MIP�ڵ���־�������õ�Ƶ����ʾ�������нⷨ�Լ���Ŀ
* 3: ��ʾ����ǰ��ʾ������ӵĸ�ƽ����������ÿ���ɹ��� MIP ��ʼ�Ĵ������Ϣ���������нⷨ�ĺ���ʱ�䣨����Ϊ��λ���ͺ���ʱ�䣨��ȷ���Ա��Ϊ��λ��
* 4: ��ʾ����ǰѡ���ṩ����Ϣ�Լ����ڸ����� LP ���������Ϣ
* 5: ��ʾ����ǰѡ���ṩ����Ϣ�Լ����ڸ��ͽڵ㴦�� LP ���������Ϣ

<a id="210216-������Ϣ��ʾ"></a>
#### 2.10.2.16 ������Ϣ��ʾ
IloCplex.Param.Tune.Display

* 0, �ر���ʾ
* 1, ��ʾ��׼��ͱ��棻ȱʡֵ
* 2, ��ʾ��׼�����Լ����ڳ��ԵĲ�������
* 3, ��ʾ�꾡�ı������־

<a id="210217-�����η���Ϣ��ʾ"></a>
#### 2.10.2.17 �����η���Ϣ��ʾ
IloCplex.Param.Simplex.Display

* 0, No iteration messages until solution
* 1, Iteration information after each refactoring; default
* 2, Iteration information for each iteration

<a id="210218-mip-�ڵ���־���"></a>
#### 2.10.2.18 MIP �ڵ���־���
IloCplex.Param.MIP.Interval����ѡֵ��

* n < 0: ��ʾ�µ�ǰ�������⿪ʼʱƵ����ʾ��־�У���������ʱ��ʾ��Ƶ�ʽ��͡�
* 0: �� CPLEX ������¼�ڵ��Ƶ�ʣ�ȱʡֵ��
* n > 0: ��ʾ�µ�ǰ���ÿ�� n ���ڵ���ʾһ����־��

<a id="210219-mip-heuristic-frequency"></a>
#### 2.10.2.19 MIP heuristic frequency
IloCplex.Param.MIP.Strategy.HeuristicFreq�����ڿ���ʹ������ʽ�㷨��Ƶ�ʣ���ѡֵ��

* -1: �ر�����ʽ�㷨
* 0: Automatic: let CPLEX choose; default
* ������: Apply the periodic heuristic at this frequency


<a id="211-����"></a>
## 2.11 ����
<a id="2111-�߼�Լ��"></a>
### 2.11.1 �߼�Լ��
* IloCplexModeler.and
* IloCplexModeler.or
* IloCplexModeler.not
* IloCplexModeler.ifThen
    - For example: IloCplexModeler.ifThen(cplex.eq(varUsed[i], 0), cplex.eq(buy[i], 0.0))
* IloCplexModeler.min
* IloCplexModeler.max


<a id="3-legacy-callback"></a>
# 3 Legacy Callback
IloCplex.Callback�ඨ����֧������callback�����Ľӿڡ�callback������Ҫ�û�ʵ�֡�mian����������main������clpex�Ż����̵���Ӧ���ڵ㡱���Զ����á�Ҫʵ��callback����ѭ��

1. ѡ�񲢼̳���Ӧ��callback��

2. ʵ��main�������Զ����main��������ʹ�ø���ķ���

3. If the default implementation of the method clone is not adequate, and if the callback is to be used for parallel optimization, this method also needs to be implemented by the user. Recall that the default clone method performs a shallow copy, so typically a user implementation needs to perform a deep copy for objects that should be local to threads or the user implementation must use the synchronize keyword where synchronization is required.

4. �½��Զ���callback���ʵ����ʹ��IloCplex.use(callbackʵ��)��ӣ� ֮��IloCplex object�������ʱ��������Ӧ�ġ��ڵ㡱�����û������callback���������ܻ��õ����·�����
    * (IloLPMatrix)cplex.LPMatrixIterator().next()������cplexΪIloCplexʵ��
    * IloCplex.use
    * IloCplex.setParam
    * IloCplex.solve
    * IloCplex.end

5. The methods of this class are protected to make sure they are used only to derive a user-written callback class or to implement the main method in it.

<a id="31-�ο��ص�informational-callback"></a>
## 3.1 �ο��ص�Informational callback
<a id="311-���"></a>
### 3.1.1 ���
�ο��ص����û���д�����̣������������ԣ�

* ʹӦ�ó����ܹ����ʹ��ڵ�ǰ��������滮 (MIP) �Ż�����Ϣ������������
* ������Ž�ռ������
* �ο��ص�������ʹӦ�ó����ܹ���ֹ�Ż�
* ��MIP��̬�������ݡ��������ģ�ͣ�MIP��̬�������Աȳ���MIP��֧�ü������ҵ����н�����Ž�
* �벢���Ż������з�ʽ����
* CPLEXȷ�����̰߳�ȫ��ʽ����ȷ����˳����òο��ص�

<a id="312-�漰����"></a>
### 3.1.2 �漰����
ilog.cplex.IloCplex.MIPInfoCallback���ɲ鿴�ɷ��ص���Ϣ�������������£�

* IloCplex.DisjunctiveCutInfoCallback
* IloCplex.FlowMIRCutInfoCallback
* IloCplex.FractionalCutInfoCallback
* IloCplex.ProbingInfoCallback

<a id="313-ʾ���ļ�mipex4java"></a>
### 3.1.3 ʾ���ļ�MIPex4.java
<a id="3131-����һ���������ʱ���gap���Ƴ����Ƿ���ֹ"></a>
#### 3.1.3.1 ����һ���������ʱ���gap���Ƴ����Ƿ���ֹ
* getMIPRelativeGap()
* getCplexTime()

<a id="3132-���ܶ�����ӡ��־"></a>
#### 3.1.3.2 ���ܶ�����ӡ��־
* ��Ѱ���˸��õĽ�
    - hasIncumbent()
    - getIncumbentObjValue()
    - getIncumbentValues()
* ÿ��100��Node��ӡһ��
    - getNremainingNodes64()

<a id="32-��ѯ����ϻص�query-or-diagnostic-callbacks"></a>
## 3.2 ��ѯ����ϻص�Query or diagnostic callbacks
<a id="321-���"></a>
### 3.2.1 ���
��ѯ�ص�����ϻص����Լ������ڽ��е��Ż������������ص㣺

* ��ѡ���Ե���ֹ����
* ��ִ�вο��ص���ȣ���ѯ�ص����ʹ��ڵ�ǰ�Ż��ĸ���ϸ��Ϣ���������ǣ����ܻ��������
* �붯̬����������
* �ͳ����֧�ü����ĺ�Խ���м��裻�ڶ�̬�����ڼ�����ڲ����Ż��е�ȷ���������ڼ䣬���ڻ�������滮 (MIP) ����Щ������ܴ���

<a id="322-����λ��"></a>
### 3.2.2 ����λ��
* �ڴ��ڵ�⵽�����η����׵�ת���ڼ䣬�����ڵ���ת����ѯ�ص�
    - IloCplex.CrossoverCallback
* �����絥���η��㷨�ڼ䣬�����ڵ��������ѯ�ص�
    - IloCplex.NetworkCallback
* ���ڵ㷨�㷨�ڼ��ÿ�ε����У��������ڵ��ѯ�ص�
    - IloCplex.BarrierCallback
    - IloCplex.ContinuousCallback
* �ڵ����η��㷨�ڼ��ÿ�ε����У������õ����η���ѯ�ص�
    - IloCplex.SimplexCallback
    - IloCplex.ContinuousCallback
* �ڷ�֧�ü������ڼ䣬�����ڵ��� MIP ��ѯ�ص�
    - IloCplex.MIPCallback
* ��̽���ڼ䣬�����ڵ���̽���ѯ�ص�
    - IloCplex.ProbingCallback
* ������С����ƽ���ڼ䣬�����ڵ���С����ƽ���ѯ�ص�
    - IloCplex.FractionalCutCallback
* �����ɷ���ʽ��ƽ���ڼ䣬�����ڵ��÷���ʽ��ƽ���ѯ�ص�
    - IloCplex.DisjunctiveCutCallback
* ���������ͻ���������� (MIR) ��ƽ���ڼ䣬�����ڵ������� MIR ��ƽ���ѯ�ص�
    - IloCplex.FlowMIRCutCallback

<a id="33-���ƻص�"></a>
## 3.3 ���ƻص�
<a id="331-���"></a>
### 3.3.1 ���
���ƻص�����������MIP�����Ż��ڼ�ִ�еķ�֧�ü����������������ص㣺

* ���ƻص����Ԥ��������ʹ��Cplex�رն�̬����
* ȱʡ����£�Cplex���Բ��з�ʽ���У�������MIP���Ҳ���ڹر�״̬
* ����ͨ�����̲߳�������Ϊ������ֵ�����ò�����⣬�������ر�ע��ص�������ʵ�ֲ���ʵ��ȷ������������

<a id="332-ʹ�ó���"></a>
### 3.3.2 ʹ�ó���
<a id="3321-�ڵ�ص�"></a>
#### 3.3.2.1 �ڵ�ص�
* IloCplex.NodeCallback
* �ڷ�֧�ü������ڼ��ѯCPLEX��Ҫ�������һ���ڵ㲢ѡ���Եؼ��Ը���

<a id="3322-���ص�"></a>
#### 3.3.2.2 ���ص�
* IloCplex.SolveCallback
* ָ�������������ڸ����ڵ㴦��� LP ���Ż���ѡ��
* ���к���
![SolveCallback](./pictures/callback_method/SolveCallback.png)

<a id="3323-�û���ƽ��ص�"></a>
#### 3.3.2.3 �û���ƽ��ص�
* IloCplex.UserCutCallback
* ��ÿ���ڵ㴦����ض���������û������ƽ��
* ��ϣ��Cplex�����и�ƽ��������֮��������Զ����Cut���ж�isAfterCutLoop()ΪTure����ִ�д��뼴��
* ���к���
![UserCutCallback Method](./pictures/callback_method/UserCutCallback.png)

<a id="3324-����Լ���ص�"></a>
#### 3.3.2.4 ����Լ���ص�
* IloCplex.LazyConstraintCallback
* ��Ӷ���Լ��������Υ�������򲻻����������Լ����
* ���к���
![LazyConstraintCallback Method](./pictures/callback_method/LazyConstraintCallback.png)

<a id="3325-̽�Իص�"></a>
#### 3.3.2.5 ̽�Իص�
* IloCplex.HeuristicCallback
* ʵ��̽�ԣ���̽�Խ����Ը���ÿ���ڵ㴦��LP�ɳڽ������µ����ν�

<a id="3326-��֧�ص�"></a>
#### 3.3.2.6 ��֧�ص�
* IloCplex.BranchCallback
* ��ѯCPLEX��ÿ���ڵ㴦���з�֧�ķ�ʽ��ѡ���Եؼ��Ը���

<a id="3327-���ν�ص�"></a>
#### 3.3.2.7 ���ν�ص�
* IloCplex.IncumbentCallback
* ��� CPLEX �������ڼ��ҵ������νⲢѡ���Ե����Ծܾ�


<a id="34-�ص�����ֹ"></a>
## 3.4 �ص�����ֹ
����IloCplex.Aborter ��ʵ�����ݸ� IloCplex ��ʵ���� Ȼ�󣬵���IloCplex.Aborter.abort ��������ֹ�Ż���

<a id="35-legacy-callbackʾ��"></a>
## 3.5 Legacy Callbackʾ��
<a id="351-admipex1-node-and-branch-callbacks"></a>
### 3.5.1 AdMIPex1: node and branch callbacks
<a id="3511-branch-callbacks"></a>
#### 3.5.1.1 branch callbacks
1. �̳� **IloCplex.BranchCallback** �����Լ��ķ�֧�࣬���������Լ����췽��:
    * IloNumVar[] _vars

2. ʵ��main�����������õ��ķ������£�
    * �жϷ�֧����
        - getBranchType()
        - IloCplex.BranchType.BranchOnVariable
    * ѡ���֧����
        - getFeasibilities()
        - IloCplex.IntegerFeasibilityStatus.Infeasible
    * �����֧
        - makeBranch()
        - IloCplex.BranchDirection.Up / Down

3. �����Զ����BranchCallback����

<a id="3512-node-callbacks"></a>
#### 3.5.1.2 node callbacks
1. �̳� **IloCplex.NodeCallback** �����Լ��ķ�֧��

2. ʵ��main�����������õ��ķ������£�
    * getInfeasibilitySum()
    * selectNode()

3. �����Զ����NodeCallback����

<a id="352-admipex3-special-ordered-sets-type-1"></a>
### 3.5.2 AdMIPex3: Special Ordered Sets Type 1
1. �̳� **IloCplex.BranchCallback** �����Լ��ķ�֧�࣬����������(IloSOS1)�����췽��
    * IloSOS1[] _sos

2. ʵ��main�����������õ��ķ������£�
    * ѡ���֧����
        - getFeasibilities()
        - IloCplex.IntegerFeasibilityStatus.Infeasible
        - getNumVars
    * �����֧
        - makeBranch()
        - IloCplex.BranchDirection

3. �����Զ����BranchCallback����

<a id="353-admipex2-heuristiccallback"></a>
### 3.5.3 AdMIPex2: HeuristicCallback
1. �̳� **IloCplex.HeuristicCallback** �����Լ�������ʽ�࣬���������Լ����췽��
    * IloNumVar[] _vars;

2. ʵ��main�����������õ��ķ������£�
    * ��������
        - getFeasibilities()
        - IloCplex.IntegerFeasibilityStatus.Infeasible
    * �����µĽ�
        - setSolution()

3. �����Զ����HeuristicCallback���࣬���ܻ��õ��ķ������£�
    - IloCplex.getNSOS1()
    - IloCplex.SOS1iterator()

<a id="354-admipex4-usercutcallback-and-lazyconstraintcallback"></a>
### 3.5.4 AdMIPex4: UserCutCallback and LazyConstraintCallback
1. ֱ�Ӷ���makeCuts�����������µ�CutԼ��������IloRange����

2. ���cuts
    cplex.addUserCuts()
    cplex.addLazyConstraints()

<a id="355-admipex5-usercutcallback-and-lazyconstraintcallback"></a>
### 3.5.5 AdMIPex5: UserCutCallback and LazyConstraintCallback
<a id="3551-usercutcallback"></a>
#### 3.5.5.1 UserCutCallback
To separate some constraints tend to be violated in LP relaxation dynamically

1. �̳� **IloCplex.UserCutCallback** �����Լ���UserCut�࣬���������Լ����췽��
    * IloModeler modeler
    * IloNumVar[] vars

2. ʵ��main�����������õ��ķ������£�
    * ���Cut
        - add()
        - IloCplex.CutManagement.UseCutPurge(may be purged by cplex if it's ineffective)

3. �����Զ����UserCutCallback����

<a id="3552-usercutcallback"></a>
#### 3.5.5.2 UserCutCallback
Cuts that will be scanned every time.

1. �̳� **IloCplex.UserCutCallback** �����Լ���UserCut��

2. ʵ��main�����������õ��ķ������£�
    * ���Cut
        - (IloRange)cut.getLB()
        - (IloRange)cut.getUB()

3. �����Զ����UserCutCallback����

<a id="3553-lazyconstraintcallback"></a>
#### 3.5.5.3 LazyConstraintCallback
1. �̳� **IloCplex.LazyConstraintCallback** �����Լ���LazyCut��
    * IloModeler modeler
    * IloNumVar[] vars

2. ʵ��main�����������õ��ķ������£�
    * Լ������
        - IloLinearNumExpr sum = modeler.linearNumExpr()
        - sum.addTerm(1.0, supply[c][j])
        - IloCplex.IntegerFeasibilityStatus.Infeasible
    * ���Cut
        - add(modeler.le(sum, 0.0))

3. �����Զ����LazyConstraintCallback����

<a id="356-admipex6-solvecallback��passing-in-a-solution-for-the-root-node"></a>
### 3.5.6 AdMIPex6: SolveCallback��passing in a solution for the root node
1. �̳� **IloCplex.SolveCallback** �����Լ�������ʽ�࣬���������Լ����췽��
    * IloNumVar[] _vars;

2. ʵ��main�����������õ��ķ������£�
    * ���ý�
        - setStart()

3. �����Զ����SolveCallback���࣬���ܻ��õ��ķ������£�
    - IloConversion relax = IloCplex.conversion(lp.getNumVars(), IloNumVarType.Float)
    - cplex.add(relax)
    - cplex.delete(relax)


<a id="4-generic-callback"></a>
# 4 Generic Callback
<a id="41-���"></a>
## 4.1 ���
ͨ�ûص����������ڼ�����಻ͬλ�õ��õĻص������� **`IloCplex.Callback.Function�ӿ�ʵ�֣���Ҫ����invoke������`** ���������ص㣺

* �붯̬�������ݡ�
* ��������κ� MIP ���ܡ�
* ���ӽ����Լ�����������
* ����ר�Ŵ���ԭʼģ�ͣ�������ĳЩ������⣬��Ȩ����Ԥ���ģ�ͺ��й�Ԥ���ģ�͵Ŀ�����Ϣ��
* ������ʽ���� CPLEX ʹ�õ��߳�����
* ������ʽ���л����߳�����лص���ִ�С�
* `�ṩ�Ⱦɻص����ߵ�����ԣ����ڵ���ʱ���ݻص��������ģ�Context����������Ӧ�Ĳ���`

<a id="42-����"></a>
## 4.2 ����
* ��ѯ�йص�ǰ���״̬�ͽ��ȵ���Ϣ
* ����̽�Խ�
* �����������н���Ϊ��ѡֵ
* ��ȡ��ǰ�ɳڽ�
* ����û���ƽ��
* ǿ����ֹ 

**`Attention:ͨ�ûص���ʱ��֧��:`**  
1. �Զ����Branching�� Node Selection��user solution of node problems  
2. ���ܺ�Legacy Callback����  
3. ��������Continuous problems  
4. ��Ҫ�û�ȷ���̰߳�ȫ  

<a id="43-ͨ�ûص���������context"></a>
## 4.3 ͨ�ûص���������Context
CPLEX����ͨ�ûص�ʱ������������ȷ���ɴӸõ��ûص�����ִ�еĲ�����

<a id="431-ilocplexcallbackcontextid�е������ĳ���"></a>
### 4.3.1 IloCplex.Callback.Context.Id�е������ĳ���
<a id="4311-threadup"></a>
#### 4.3.1.1 ThreadUp
* This constant is used to specify CPLEX generic callback invocation when CPLEX activates a thread. 

<a id="4312-threaddown"></a>
#### 4.3.1.2 ThreadDown
* This constant is used to specify CPLEX generic callback invocation when CPLEX de-activates a thread.

<a id="4313-localprogress"></a>
#### 4.3.1.3 LocalProgress
* CPLEX invokes the generic callback in this context when it has made thread-local progress. 
* Thread-local progress is progress that happened on one of the threads used by CPLEX but has not yet been committed to global solution structures. 
* Information queried from a callback invoked in this context is valid only in the calling thread.
* The current information about the solution process can be queried with these routines: `getIntInfo()` and `getLongInfo()`, and `getIncumbent()`.

<a id="4314-globalprogress"></a>
#### 4.3.1.4 GlobalProgress
* CPLEX invokes the generic callback in this context when it has made global progress, that is, when new information has been committed to the global solution structures. 
* You can query the current globally valid information about the solution process with the routines `getIntInfo()` and `getLongInfo()`, and `getIncumbent()`.

<a id="4315-candidate"></a>
#### 4.3.1.5 Candidate
* CPLEX invokes the generic callback when it has found a new candidate for an integer-feasible solution or has encountered an unbounded relaxation. CPLEX offers the callback a chance to reject the candidate solution or the unbounded relaxation.
    - If `isCandidatePoint()` shows that CPLEX has found a candidate feasible point, then you can query that point by using `getCandidatePoint()`

    - If `isCandidateRay()` shows that CPLEX has encountered an unbounded relaxation, then you can get the unbounded ray from `getCandidateRay()`

    - In either the case, the user can reject the feasible point or unbounded direction by means of the routine `rejectCandidate()`
* Use the constant `Candidate` in two different ways:
    - As a value passed into the generic callback function to specify in which context the generic callback is invoked
    - As a bit-wise OR with the where argument of the routine CPXXcallbacksetfunc and CPXcallbacksetfunc to specify in which situations CPLEX should invoke the generic callback

<a id="4316-relaxation"></a>
#### 4.3.1.6 Relaxation
* CPLEX invokes the generic callback in this context when it has found a relaxed solution available. The relaxed solution is usually not integer feasible.
* You can query the relaxed solution with the routine `getRelaxationPoint()`.

<a id="432-ʹ�÷���"></a>
### 4.3.2 ʹ�÷���
1. ���塰���������롱
    * long contextMask = IloCplex.Callback.Context.Id.Relaxation
    * ���Խ��а�λ���򡱲�����contextMask |= IloCplex.Callback.Context.Id.Candidate

2. IloCplex.use(IloCplex.Callback.Function, contextMask)

3. ���÷����ܽ�
![Context���÷����ܽ�](./pictures/context_method.png)

<a id="44-generic-callbackʾ��"></a>
## 4.4 Generic Callbackʾ��
<a id="441-admipex8-cut"></a>
### 4.4.1 AdMIPex8: Cut
1. �̳� **IloCplex.Callback.Function�ӿ�** ����ͨ�ûص��࣬���������Լ����췽��

2. contextMask = IloCplex.Callback.Context.Id.Relaxation | IloCplex.Callback.Context.Id.Candidate

3. �ֱ�ʵ�ּ��ֲ�ͬ�����Ķ�Ӧ����
    * disaggregate()
        - ��� Id = Relaxation �����
        - Ŀ�ģ�add disagrregated constraints linking clients and location
        - context.addUserCut()���Cut��ʹ��IloCplex.CutManagement.UseCutPurge
    * cutsFromTable()����
        - ��� Id = Relaxation �����
        - Ŀ�ģ�Uses a static table of cuts and scans this table for violated cuts
        - context.addUserCut()���Cut��ʹ��IloCplex.CutManagement.UseCutPurge
    * lazyCapacity()
        - ��� Id = Candidate �����
        - ����isCandidatePoint()�ж�
        - ���Լ��
        - context.rejectCandidate()

4. ����invoke����������contextֵ��ȡ��Ӧ�Ĳ���

5. ʹ��IloCplex.use(Function callback, long contextMask)��ͨ�ûص���ӵ�Cplex��

<a id="442-admipex9-heuristiccallback"></a>
### 4.4.2 AdMIPex9: HeuristicCallback
1. �̳� **IloCplex.Callback.Function�ӿ�** ����ͨ�ûص��࣬���������Լ����췽��

2. contextMask = IloCplex.Callback.Context.Id.Relaxation | IloCplex.Callback.Context.Id.Candidate

3. ����ʽ�㷨������ƣ�������roundDownȡ��ʾ��
    * context.postHeuristicSolution()�������ʽ�⵽������

4. ����invoke����������contextֵ��ȡ��Ӧ�Ĳ���

5. ���ͨ�ûص���Cplex��
    * �ر�Cplex������ʽ�㷨��cplex.setParam(IloCplex.Param.MIP.Strategy.HeuristicFreq, -1);
    * ʹ��IloCplex.use(Function callback, long contextMask)��ͨ�ûص���ӵ�Cplex��


<a id="5-cplex-�ٷ�ʾ��˵��"></a>
# 5 Cplex �ٷ�ʾ��˵��
| Example | Description |
|:-|:-|
| AdMIPex1.java | ʹ�ýڵ�ͷ�֧�ص����Ż� MIP |
| AdMIPex2.java | ʹ������ʽ�ص����Ż� MIP |
| AdMIPex3.java | �Ծ����������򼯺� (SOS) �� MIP ʹ�÷�֧�ص� |
| AdMIPex4.java | ������ʾ�����Ӷ���Լ�����û���ƽ�� |
| AdMIPex5.java | ����ͨ���� MIP �ĸ�ƽ��ص�����Ӹ�ƽ�� |
| AdMIPex6.java | ���ڴ� LP ������ MIP �Ż� |
| AdMIPex8.java | ʹ�������ڽⷨ�������е����ڵ��Ż����Ͷ�ż�Ż�����ͨ�ûص� |
| AdMIPex9.java | ʹ�����ڵ�������ʽ��ͨ�ûص� |
| Benders.java | ������ʾ Benders �ֽ� |
| BendersATSP.java | ������ʾ�ǶԳ�����������Ա��������� Benders �ֽ��жԶ����������� LP �ⷨ�Ķ���Լ���ص��Լ��Զ���С�������� LP �ⷨ���û���ƽ��ص� |
| Blend.java | ���ڶԻ������������ |
| CplexServer.java | ����˵������ڱ��� J2EE �ͻ���Ӧ�ó����������� IloCplexModeler ����д���ܴ� Java ģ�͵��Ż������� |
| CutStock.java | ����һ������˵�������ɵ�����ģ�� |
| Diet.java | ���Ǿ�����ʳ��������ʹ�� Java ���Ե�ʵ�֣����Թ滮�����԰��У�����ʳ���������ʳƷ�����У�����ʳ����������������� |
| Etsp.java | ������������ӳٳɱ���صĵ�������ʹ�� Java ���Ե�ʵ�� |
| Facility.java | ���ڶԲֿ�λ������������ | ����ѡ��ʾ����Ӧ�� Benders �ֽ� |
| FixCost1.java | ���ڶ���̶��ɱ���ص������滮���������� |
| FoodManufact.java | ����ʵʩ�� H. P. Williams �Ľ�ģ�̿���������ʳƷ�����滮����Ľ� |
| GlobalQPex1.java | ����˵����ζ�ȡ͹����͹����ι滮ģ�� (QP) ���߻���������ι滮ģ�� (MIQP) �Լ���ζ����������Ի��һ�׻�ȫ�����Ž� |
| Goalex1.java | ʹ��Ŀ�� API ���зֲ� |
| Goalex2.java | ʹ��Ŀ�� API ����Ӹ�ƽ�� |
| Goalex3.java | ʹ��Ŀ�� API ����ӽڵ����������������� Goalex1.java |
| IndefQPex1.java | �������벻ȷ�����ι滮���� PSD QP���������������Ի�þֲ����Ž� |
| InOut1.java | ����һ������ģ�� |
| InOut3.java | ������һ������ģ�� |
| LPex1.java | ����һ������˵��������䷽���Ļ������Թ滮ģ�� |
| LPex2.java | ����һ���������Թ滮ģ�ͣ������ļ��е����� |
| LPex3.java | ����˵�������ģ����������Լ���������Ż� |
| LPex4.java | ����˵���ص� |
| LPex6.java | ����˵�����װ����� |
| LPex7.java | ����˵����η��������� |
| MIPex1.java | ����һ������ MIP ģ�� |
| MIPex2.java | ������һ������ MIP ģ�� |
| MIPex3.java | ���� MIP ģ���е��������򼯺� (SOS) |
| MIPex4.java | ����˵����δ����ο��ص��Լ�����������־��¼�����ƽڵ������ж��Ż������⣬������˵�������ֹ�Ż��Լ����ʹ��ʱ����� |
| MIQPex1.java | ����һ������������ι滮ģ�ͣ������� MIP �еĶ���Ŀ�� |
| MixBlend.java | ����һ�� MIP ���ģ�� |
| Populate.java | ����˵������ڽ�������ɺͱ������� |
| QPex1.java | ���� LP �еĶ���Ŀ�� |
| QPex2.java | ������һ�����ж���Ŀ���ģ�� |
| QPex3.java | �Զ��α��ʽʹ�� Concert Technology �ӿڣ��Ա�ʹ�ö��α��ʽ��������޸�Ŀ�꺯���е�ģ�� |
| Rates.java | ���ڶ��������������صĹ滮���������� |
| SocpEx1.java | ����˵����η��� SOCP ģ���еĶ�żֵ�������ɱ� |
| QCPDual.java | ����˵����η��ʶ���Լ���滮ģ�� (QCP) �еĶ�żֵ�������ɱ� |
| Steel.java | ���ڶ�˵����ģ�͹��������������滮���������⣻������ Fourer��Gay �� Kernighan �������� AMPL ��ģ�鼮�е� steelT.mod |
| Transport.java | ʹ�÷ֶ����Գɱ����� |
| TuneSet.java | ���ڷ���һ��ģ���Լ��ṩ����ķ�ȱʡ����������������� |
| Warehouse.java | ����һ���ֿ�λ�����⣻��ʹ��Ŀ�� |
| InputDataReader.java | ��һЩʾ�����ڶ�ȡ���� |