---
title: "Обнуляемые типы значений (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Nullable
dev_langs:
- VB
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9cdf1864fe955a082936596821ee84c831b86444
ms.lasthandoff: 03/13/2017

---
# <a name="nullable-value-types-visual-basic"></a>Типы значения, допускающие Null (Visual Basic)
Иногда пользователь работает с типом значения, не имеет определенное значение в определенных обстоятельствах. Например поле в базе данных может потребоваться различать наличие присвоенного значения, имеет смысл и отсутствие присвоенного значения. Типы значений можно использовать обычные значения или значение null. Такое расширение называется *обнуляемый тип*.  
  
 Каждый тип nullable создается из универсального <xref:System.Nullable%601>структуры.</xref:System.Nullable%601> Рассмотрим базу данных, которая отслеживает должностных обязанностей. В следующем примере создается допускающее `Boolean` типа и объявляется переменная этого типа. Можно написать объявление тремя способами:  
  
 [!code-vb[VbVbalrNullableValue&#1;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_1.vb)]  
  
 Переменная `ridesBusToWork` может содержать значение `True`, значение `False`, или без значения. Его начальное значение по умолчанию значение Нет, который в этом случае может означать, что данные не еще были получены для этого пользователя. Напротив `False` может означать, что данные были получены, и пользователь не подходите к шине для работы.  
  
 Можно объявить переменные и свойства с типами nullable, и можно объявить массив элементов типа nullable. Можно объявить процедуру с типами nullable в качестве параметров, и можно также возвращать тип nullable из `Function` процедуры.  
  
 Не удается создать тип nullable на ссылочном типе, такие как массив, `String`, или класс. Базовый тип должен быть типом значения. Дополнительные сведения см. в разделе [типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
## <a name="using-a-nullable-type-variable"></a>Использование обнуляемый тип переменной  
 Самые важные члены типа nullable являются его <xref:System.Nullable%601.HasValue%2A>и <xref:System.Nullable%601.Value%2A>Свойства.</xref:System.Nullable%601.Value%2A> </xref:System.Nullable%601.HasValue%2A> Для переменной типа nullable <xref:System.Nullable%601.HasValue%2A>Указывает, содержит ли переменная определенное значение.</xref:System.Nullable%601.HasValue%2A> Если <xref:System.Nullable%601.HasValue%2A>является `True`, можно считать значение из <xref:System.Nullable%601.Value%2A>.</xref:System.Nullable%601.Value%2A> </xref:System.Nullable%601.HasValue%2A> Обратите внимание, что оба <xref:System.Nullable%601.HasValue%2A>и <xref:System.Nullable%601.Value%2A>являются `ReadOnly` свойства.</xref:System.Nullable%601.Value%2A> </xref:System.Nullable%601.HasValue%2A>  
  
### <a name="default-values"></a>Значения по умолчанию  
 При объявлении переменной с типом, допускающим значение NULL, его <xref:System.Nullable%601.HasValue%2A>свойство имеет значение по умолчанию `False`.</xref:System.Nullable%601.HasValue%2A> Это означает, что по умолчанию переменная не имеет заданного значения, вместо значения по умолчанию значение базового типа. В следующем примере переменная `numberOfChildren` изначально не имеет заданного значения, даже если значение по умолчанию `Integer` тип равен 0.  
  
 [!code-vb[VbVbalrNullableValue&#2;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_2.vb)]  
  
 Значение null полезно для обнаружения неопределенного или неизвестного значения. Если `numberOfChildren` был объявлен как `Integer`, будет не значение, которое могло бы указать, что данные еще не доступных в настоящее время.  
  
### <a name="storing-values"></a>Сохранение значений  
 Сохраните значение в переменной или свойстве типа nullable обычным образом. Следующий пример присваивает значение переменной `numberOfChildren` объявленного в предыдущем примере.  
  
 [!code-vb[VbVbalrNullableValue&#3;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_3.vb)]  
  
 Если переменная или свойство типа nullable содержит заданное значение, может вызвать его, чтобы вернуться к исходному состоянию отсутствия присвоенное значение. Это можно сделать, задав переменную или свойство `Nothing`, как показано в следующем примере.  
  
 [!code-vb[VbVbalrNullableValue&#4;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_4.vb)]  
  
> [!NOTE]
>  Хотя можно присвоить `Nothing` переменной типа nullable, но нельзя проверить ее для `Nothing` с помощью знака равенства. Сравнение, использующее знак равенства `someVar = Nothing`, всегда имеет значение `Nothing`. Можно проверить свойства переменных <xref:System.Nullable%601.HasValue%2A>свойство `False`, или проверить с помощью `Is` или `IsNot` оператор.</xref:System.Nullable%601.HasValue%2A>  
  
### <a name="retrieving-values"></a>Получение значений  
 Чтобы получить значение переменной типа nullable, следует сначала проверить ее <xref:System.Nullable%601.HasValue%2A>свойство, чтобы убедиться, что он имеет значение.</xref:System.Nullable%601.HasValue%2A> При попытке прочитать значение при <xref:System.Nullable%601.HasValue%2A>— `False`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] вызывает <xref:System.InvalidOperationException>исключение.</xref:System.InvalidOperationException> </xref:System.Nullable%601.HasValue%2A> В следующем примере показано рекомендуемый способ чтения переменной `numberOfChildren` из предыдущего примера.  
  
 [!code-vb[VbVbalrNullableValue&#5;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_5.vb)]  
  
## <a name="comparing-nullable-types"></a>Сравнение обнуляемые типы  
 Если значения NULL `Boolean` в логических выражениях используются переменные, результат может быть `True`, `False`, или `Nothing`. Ниже приведена таблица истинности для `And` и `Or`. Поскольку `b1` и `b2` теперь имеют три возможных значения, существует девять комбинаций для оценки.  
  
|B1|B2|B1 и b2|B1 или b2|  
|--------|--------|---------------|--------------|  
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|  
|`Nothing`|`True`|`Nothing`|`True`|  
|`Nothing`|`False`|`False`|`Nothing`|  
|`True`|`Nothing`|`Nothing`|`True`|  
|`True`|`True`|`True`|`True`|  
|`True`|`False`|`False`|`True`|  
|`False`|`Nothing`|`False`|`Nothing`|  
|`False`|`True`|`False`|`True`|  
|`False`|`False`|`False`|`False`|  
  
 Если значение логической переменной или выражения равно `Nothing`, он не является ни `true` , ни `false`. Рассмотрим следующий пример.  
  
 [!code-vb[VbVbalrNullableValue №&6;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_6.vb)]  
  
 В этом примере `b1 And b2` равен `Nothing`. В результате `Else` предложение выполняется в каждом `If` инструкции и вывод выглядит следующим образом:  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  `AndAlso`и `OrElse`, которые используют сокращенные вычисления, должны оценивать свои вторые операнды, если первый `Nothing`.  
  
## <a name="propagation"></a>Распространение  
 Если один или оба операнда арифметические, сравнения, сдвига или тип операции, допускающие значения NULL, результат операции также допускает значение NULL. Если оба операнда имеют значения, которые не являются `Nothing`, операция выполняется на основных значениях операндов, как если бы ни был тип nullable. В следующем примере переменные `compare1` и `sum1` неявным. Если навести указатель мыши на их вы увидите, что компилятор выводит для них обоих обнуляемые типы.  
  
 [!code-vb[VbVbalrNullableValue&#7;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_7.vb)]  
  
 Если один или оба операнда имеют значение `Nothing`, результатом будет `Nothing`.  
  
 [!code-vb[VbVbalrNullableValue №&8;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_8.vb)]  
  
## <a name="using-nullable-types-with-data"></a>Использование допускающих значение NULL типов с данными  
 База данных — одно из наиболее важных мест для используют обнуляемые типы. Не все объекты базы данных в настоящее время поддерживают типы nullable, но адаптеры таблицы, созданные конструктором. В разделе «Поддержки TableAdapter для обнуляемых типов» в [TableAdapter Overview](https://docs.microsoft.com/visualstudio/data-tools/tableadapter-overview).  
  
## <a name="see-also"></a>См. также  
 <xref:System.InvalidOperationException></xref:System.InvalidOperationException>   
 <xref:System.Nullable%601.HasValue%2A></xref:System.Nullable%601.HasValue%2A>   
 [Использование допускающих значение NULL типов](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)   
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Устранение неполадок типы данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Обзор класса TableAdapter](https://docs.microsoft.com/visualstudio/data-tools/tableadapter-overview)   
 [Если оператор](../../../../visual-basic/language-reference/operators/if-operator.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md)   
 [Оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md)
