# Graph creation of EFIN relationships found in Return Year


```python
import networkx as nx
import matplotlib as plt
import pandas as pd
import graphviz
import os
os.environ["PATH"] += os.pathsep + 'C:/Program Files (x86)/Graphviz2.38/bin/'
```

Input Dataframe: 2016 Return


```python
print(pd.DataFrame(data=[[1234,'888-888-8888',2345,'Deb T','Deb T']], columns=['EFIN','Orig_phone','ptin','Signed_name','Orig_signed_name']).to_string(index=False))
```

    

Edge Schema/ MetaData (node type displayed)


```python
ef1 = graphviz.Digraph(); ef2 = graphviz.Digraph(); ef3 = graphviz.Digraph()
ef1.edge('efin','phone'); ef2.edge('efin','ptin'); ef3.edge('efin','name')
#ef3.edge_attr.update(arrowhead='vee', arrowsize='2')
ef1.graph_attr['rankdir'] = 'LR'; ef2.graph_attr['rankdir'] = 'LR'; ef3.graph_attr['rankdir'] = 'LR'
```


```python
ef1
```

```python
ef2
```

```python
ef3
```


```python
efin = graphviz.Digraph()
efin.node('A', 'EFIN: 1234')
efin.node('B', 'Phone: 888-888-8888')
efin.node('C', 'PTIN: 2345')
efin.node('D', 'Name: Deb T')
efin.edges(['AB', 'AC', 'AD'])
efin.graph_attr['rankdir'] = 'LR'
efin
```


var edgesDst = List(("EfinToPhone_Return_2016","orig_phone","phone"),("EfinToPtin_Return_2016","ptin","ptin"), ("EfinToSigned_Name_Return_2016","signed_name","name"),("EfinToOrig_Signed_Name_Return_2016","orig_signed_name","name"))
ReturnYear=2016
val g_sr2016 = buildSourceGraphFromEdges(smRet_ETA2016,"edge_r2016","vert_r2016") 
g_sr2016.vertices.count
//res40: Long = 78005319 

ReturnYear=2017
edgesDst = List(("EfinToPhone_Return_2017","orig_phone","phone"),("EfinToPtin_Return_2017","ptin","ptin"), ("EfinToSigned_Name_Return_2017","signed_name","name"),("EfinToOrig_Signed_Name_Return_2017","orig_signed_name","name"))
val g_sr2017 = buildSourceGraphFromEdges(smRet_ETA2017,"edge_r2017","vert_r2017") 
g_sr2017.vertices.count
