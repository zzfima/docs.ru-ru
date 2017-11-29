---
title: "Типы значения, допускающие Null (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8734114b9d657066a0ef0b2d648f0290c03b1cbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="nullable-value-types-visual-basic"></a>Типы значения, допускающие Null (Visual Basic)
Иногда пользователь работает с типом значения, не имеет определенного значения в определенных обстоятельствах. Например поле в базе данных может потребоваться различать наличие присвоенного значения, имеет смысл и отсутствие присвоено значение. Типы значений можно расширить выполнить обычные значения или значение null. Такое расширение называется *обнуляемый*.  
  
 Каждый тип nullable создается на основе универсального <xref:System.Nullable%601> структуры. Рассмотрим базу данных, отслеживающий должностных обязанностей. В следующем примере создается допускающему значение NULL `Boolean` введите и объявляется переменная этого типа. Можно написать объявление тремя способами:  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_1.vb)]  
  
 Переменная `ridesBusToWork` может содержать значение `True`, значение `False`, или без значения. Его начальное значение по умолчанию имеет никакого смысла, который в этом случае может означать, что данные не еще были получены для этого пользователя. Напротив `False` может означать, что данные были получены лицо не велосипеде шины для работы.  
  
 Можно объявить переменные и свойства с типами nullable, и можно объявить массив элементов типа nullable. Можно объявить процедуру с типами nullable в качестве параметров, и может возвращать тип nullable из `Function` процедуры.  
  
 Не удается создать тип nullable для ссылочного типа, такого как массив, `String`, или класс. Базовый тип должен быть типом значения. Дополнительные сведения см. в разделе [типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
## <a name="using-a-nullable-type-variable"></a>С помощью переменной типа значения NULL  
 Наиболее важные члены типа nullable являются его <xref:System.Nullable%601.HasValue%2A> и <xref:System.Nullable%601.Value%2A> свойства. Для переменной типа nullable <xref:System.Nullable%601.HasValue%2A> указывает, содержит ли переменная определенное значение. Если <xref:System.Nullable%601.HasValue%2A> — `True`, можно считать значение из <xref:System.Nullable%601.Value%2A>. Обратите внимание, что оба <xref:System.Nullable%601.HasValue%2A> и <xref:System.Nullable%601.Value%2A> , `ReadOnly` свойства.  
  
### <a name="default-values"></a>Значения по умолчанию  
 При объявлении переменной с типом nullable его <xref:System.Nullable%601.HasValue%2A> свойство имеет значение по умолчанию `False`. Это означает, что по умолчанию переменная не имеет заданного значения, вместо значения по умолчанию значение базового типа. В следующем примере переменная `numberOfChildren` изначально не имеет заданного значения, даже если значение по умолчанию `Integer` тип равен 0.  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_2.vb)]  
  
 Значение null полезно для обнаружения неопределенного или неизвестного значения. Если `numberOfChildren` значения были объявлены как `Integer`, будет не значение, которое может указывать, что данные еще не доступных в настоящее время.  
  
### <a name="storing-values"></a>Сохранение значений  
 Сохраните значение в переменную или свойство типа nullable обычным образом. Следующий пример присваивает значение переменной `numberOfChildren` объявленного в предыдущем примере.  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_3.vb)]  
  
 Если переменная или свойство типа nullable содержит определенное значение, вы можете вызвать для возврата к исходному состоянию отсутствия назначенное значение. Это можно сделать, задав переменную или свойство `Nothing`, как показано в следующем примере.  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_4.vb)]  
  
> [!NOTE]
>  Несмотря на то, что можно назначить `Nothing` переменной типа nullable, нельзя проверить ее `Nothing` с помощью знака равенства. Сравнение, в котором используется знак равенства, `someVar = Nothing`, всегда равно `Nothing`. Можно проверить переменную <xref:System.Nullable%601.HasValue%2A> свойство `False`, или проверить с помощью `Is` или `IsNot` оператор.  
  
### <a name="retrieving-values"></a>Получение значений  
 Чтобы получить значение переменной типа nullable, сначала следует проверить его <xref:System.Nullable%601.HasValue%2A> свойство, чтобы убедиться, что он имеет значение. При попытке прочитать значение при <xref:System.Nullable%601.HasValue%2A> — `False`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] вызывает <xref:System.InvalidOperationException> исключение. В следующем примере показано рекомендуемый способ чтения переменной `numberOfChildren` из предыдущего примера.  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_5.vb)]  
  
## <a name="comparing-nullable-types"></a>Сравнение типов, допускающих значение NULL  
 Если значения NULL `Boolean` переменные используются в логических выражениях, результат может быть `True`, `False`, или `Nothing`. Ниже приведена таблица истинности для `And` и `Or`. Поскольку `b1` и `b2` теперь имеют три возможных значения, существует девять комбинаций для оценки.  
  
|B1|В2|B1 и В2|B1 или В2|  
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
  
 [!code-vb[VbVbalrNullableValue#6](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_6.vb)]  
  
 В этом примере `b1 And b2` равен `Nothing`. В результате `Else` предложение выполняется в каждом `If` инструкции и вывод выглядит следующим образом:  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  `AndAlso`и `OrElse`, которые используют сокращенные вычисления, должны оценивать свои вторые операнды при первой, результатом которого является `Nothing`.  
  
## <a name="propagation"></a>Распространение  
 Если один или оба операнда арифметические, сравнения, shift или тип операции, допускающие значение NULL, результат операции также допускает значение NULL. Если оба операнда имеют значения, которые не являются `Nothing`, операция выполняется на основных значениях операндов, как если бы ни был тип nullable. В следующем примере переменные `compare1` и `sum1` неявным. При наведении указателя мыши над ними вы увидите, что компилятор выводит для них типы, допускающие значение NULL.  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_7.vb)]  
  
 Если один или оба операнда имеют значение `Nothing`, это приведет к появлению `Nothing`.  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_8.vb)]  
  
## <a name="using-nullable-types-with-data"></a>Использование допускающих значение NULL типов с данными  
 Базы данных является одним из наиболее важных местах использовать типы, допускающие значение NULL. Не все объекты базы данных в настоящее время поддерживает типы, допускающие значение NULL, но адаптеры таблицы, автоматически созданный конструктором. В разделе «Поддержки адаптера таблицы для типов, допускающих значение NULL» [Общие сведения о TableAdapter](/visualstudio/data-tools/tableadapter-overview).  
  
## <a name="see-also"></a>См. также  
 <xref:System.InvalidOperationException>  
 <xref:System.Nullable%601.HasValue%2A>  
 [Использование допускающих значение NULL типов](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Общие сведения об адаптере таблиц](/visualstudio/data-tools/tableadapter-overview)  
 [Оператор If](../../../../visual-basic/language-reference/operators/if-operator.md)  
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [Оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md)
