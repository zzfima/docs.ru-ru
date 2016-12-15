---
title: "Оператор Or (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Or"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Or - оператор"
  - "Побитовые операторы [Visual Basic]"
  - "включающий оператор OR"
  - "Побитовые операторы, оператор OR"
  - "Or - ключевое слово"
  - "операторы [Visual Basic] включительно или"
  - "операторы [Visual Basic], дизъюнкция"
  - "поразрядное сравнение"
  - "логическая дизъюнкция"
  - "оператор дизъюнкции"
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор Or (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Выполняет логическое сложение двух `Boolean` выражений или побитового логического сложения двух числовых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любой `Boolean` или числовое выражение. Для `Boolean` сравнения, `result` является включающее логическое сложение двух `Boolean` значения. Для битовых операций `result` — это числовое значение, представляющее включающую побитовую дизъюнкцию двух числовых битовых шаблонов.  
  
 `expression1`  
 Обязательный. Любой `Boolean` или числовое выражение.  
  
 `expression2`  
 Обязательный. Любой `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Для `Boolean` сравнения, `result` является `False` если и оба `expression1` и `expression2` равен `False`. В следующей таблице показано, как `result` определяется.  
  
|Если `expression1` является|И `expression2` —|Значение `result` —|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  В `Boolean` сравнения, `Or` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедур.  [Оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md) выполняет *сокращенного вычисления*, означает, что если `expression1` является `True`, то `expression2` не вычисляется.  
  
 Для битовых операций `Or` оператор выполняет поразрядное сравнение одинаково расположенных битов в двух числовых выражениях и задает соответствующий бит в `result` согласно следующей таблице.  
  
|Если бит в `expression1` —|И бита `expression2` —|Бит в `result` —|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Поскольку логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические операторы и операторы отношения, побитовые операции следует заключать в круглые скобки, чтобы обеспечить правильное выполнение.  
  
## <a name="data-types"></a>Типы данных  
 Если операнды состоят из одного `Boolean` выражение и одного числового выражения, Visual Basic преобразует `Boolean` выражение в числовое значение (-1 для `True` и 0 для `False`) и выполняет битовую операцию.  
  
 Для `Boolean` сравнения, тип данных результата является `Boolean`. Поразрядное сравнение, тип данных результата является числовым типом, соответствующим типам данных `expression1` и `expression2`. В разделе «Реляционные и побитовое сравнение» [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Перегрузка  
  `Or` Оператор может быть *перегруженные*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Or` оператора для выполнения логической дизъюнкции двух выражений. В результате `Boolean` значение, представляющее ли два выражения являются `True`.  
  
 [!code-vb[VbVbalrOperators#35](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_1.vb)]  
  
 В предыдущем примере получаются результаты `True`, `True`, и `False`, соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Or` оператора для выполнения логической дизъюнкции над отдельными битами двух числовых выражений. Бит в результирующем шаблоне устанавливается в том случае, если любой из соответствующих битов в операндах равен 1.  
  
 [!code-vb[VbVbalrOperators#36](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_2.vb)]  
  
 В предыдущем примере получаются результаты 10, 14 и 14 соответственно.  
  
## <a name="see-also"></a>См. также  
 [Логические (побитовые) операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Приоритет операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md)   
 [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)