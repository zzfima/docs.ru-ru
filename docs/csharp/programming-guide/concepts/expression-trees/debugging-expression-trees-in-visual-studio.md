---
title: "Отладка деревьев выражений в Visual Studio (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
caps.latest.revision: "4"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d74df8ba339526e20850cd8b8f1a4b37c20e22ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a>Отладка деревьев выражений в Visual Studio (C#)
При отладке приложений можно анализировать структуру и содержимое деревьев выражений. Чтобы получить краткий обзор структуры дерева выражения, можно использовать свойство `DebugView`, которое доступно только в режиме отладки. Дополнительные сведения об отладке см. в разделе [Отладка в Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).  
  
 Для оптимизации представления содержимого деревьев выражений свойство `DebugView` использует визуализаторы Visual Studio. Дополнительные сведения см. в статье, посвященной [созданию пользовательских визуализаторов](/visualstudio/debugger/create-custom-visualizers-of-data).  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Открытие визуализатора дерева выражения  
  
1.  Щелкните значок лупы рядом с именем свойства `DebugView` дерева выражения в окне **Советы**, **Контрольные значения**, **Видимые** или **Локальные**.  
  
     Откроется список визуализаторов.  
  
2.  Щелкните визуализатор, который необходимо использовать.  
  
 Каждый тип выражения отображается в визуализаторе, как описано в следующих разделах.  
  
## <a name="parameterexpressions"></a>ParameterExpressions  
 В начале имен переменных <xref:System.Linq.Expressions.ParameterExpression> отображается символ "$".  
  
 Если параметр не имеет имени, оно назначается автоматически, например `$var1` или `$var2`.  
  
### <a name="examples"></a>Примеры  
  
|Выражение|Свойство `DebugView`|  
|----------------|--------------------------|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");`|`$num`|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int));`|`$var1`|  
  
## <a name="constantexpressions"></a>ConstantExpressions  
 Для объектов <xref:System.Linq.Expressions.ConstantExpression>, представляющих целочисленные значения, строки и `null`, отображается значение константы.  
  
 Для числовых типов, имеющих стандартные суффиксы, такие как литералы C#, суффикс добавляется к значению. В следующей таблице показаны суффиксы для различных числовых типов.  
  
|Тип|Суффикс|  
|----------|------------|  
|<xref:System.UInt32>|U|  
|<xref:System.Int64>|L|  
|<xref:System.UInt64>|UL|  
|<xref:System.Double>|D|  
|<xref:System.Single>|C|  
|<xref:System.Decimal>|M|  
  
### <a name="examples"></a>Примеры  
  
|Выражение|Свойство `DebugView`|  
|----------------|--------------------------|  
|`int num = 10; ConstantExpression expr = Expression.Constant(num);`|10|  
|`double num = 10; ConstantExpression expr = Expression.Constant(num);`|10D|  
  
## <a name="blockexpression"></a>BlockExpression  
 Если тип объекта <xref:System.Linq.Expressions.BlockExpression> отличается от типа последнего выражения в блоке, то тип отображается в свойстве `DebugInfo` в угловых скобках (\< и >). В противном случае тип объекта <xref:System.Linq.Expressions.BlockExpression> не отображается.  
  
### <a name="examples"></a>Примеры  
  
|Выражение|Свойство `DebugView`|  
|----------------|--------------------------|  
|`BlockExpression block = Expression.Block(Expression.Constant("test"));`|`.Block() {`<br /><br /> `"test"`<br /><br /> `}`|  
|`BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));`|`.Block<System.Object>() {`<br /><br /> `"test"`<br /><br /> `}`|  
  
## <a name="lambdaexpression"></a>LambdaExpression  
 Объекты <xref:System.Linq.Expressions.LambdaExpression> отображаются вместе со своими типами делегатов.  
  
 Если лямбда-выражение не имеет имени, оно назначается автоматически, например `#Lambda1` или `#Lambda2`.  
  
### <a name="examples"></a>Примеры  
  
|Выражение|Свойство `DebugView`|  
|----------------|--------------------------|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));`|`.Lambda #Lambda1<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);`|`.Lambda SampleLambda<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
  
## <a name="labelexpression"></a>LabelExpression  
 Если указать значение по умолчанию для объекта <xref:System.Linq.Expressions.LabelExpression>, оно будет отображаться перед объектом <xref:System.Linq.Expressions.LabelTarget>.  
  
 Маркер `.Label` указывает начало метки. Маркер `.LabelTarget` задает конечную цель перехода для целевого объекта.  
  
 Если метка не имеет имени, оно назначается автоматически, например `#Label1` или `#Label2`.  
  
### <a name="examples"></a>Примеры  
  
|Выражение|Свойство `DebugView`|  
|----------------|--------------------------|  
|`LabelTarget target = Expression.Label(typeof(int), "SampleLabel"); BlockExpression block = Expression.Block( Expression.Goto(target, Expression.Constant(0)), Expression.Label(target, Expression.Constant(-1)));`|`.Block() {`<br /><br /> `.Goto SampleLabel { 0 };`<br /><br /> `.Label`<br /><br /> `-1`<br /><br /> `.LabelTarget SampleLabel:`<br /><br /> `}`|  
|`LabelTarget target = Expression.Label(); BlockExpression block = Expression.Block( Expression.Goto(target5), Expression.Label(target5));`|`.Block() {`<br /><br /> `.Goto #Label1 { };`<br /><br /> `.Label`<br /><br /> `.LabelTarget #Label1:`<br /><br /> `}`|  
  
## <a name="checked-operators"></a>Проверяемые операторы  
 Проверяемые операторы отображаются с символом # перед оператором. Например, проверяемый оператор сложения отображается как `#+`.  
  
### <a name="examples"></a>Примеры  
  
|Выражение|Свойство `DebugView`|  
|----------------|--------------------------|  
|`Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));`|`1 #+ 2`|  
|`Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));`|`#(System.Int32)10D`|  
  
## <a name="see-also"></a>См. также  
 [Expression Trees (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (C#))  
 [Отладка в Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)  
 [Создание настраиваемых визуализаторов](/visualstudio/debugger/create-custom-visualizers-of-data)
