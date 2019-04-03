---
title: Типы значения, допускающие Null (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
ms.openlocfilehash: 437107bb522e1635dffa4a2de88c5d10d6707592
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825148"
---
# <a name="nullable-value-types-visual-basic"></a>Типы значения, допускающие Null (Visual Basic)
Иногда вы работаете с типом значения, который не имеет определенное значение в определенных обстоятельствах. Например поле в базе данных может потребоваться различать необходимости присвоено значение, допустимое и не присвоено значение. Типы значений можно расширить их нормальных значений или значение null. Такое расширение называется *обнуляемый тип*.  
  
 Каждый тип nullable создается на основе универсального <xref:System.Nullable%601> структуры. Рассмотрим базу данных, отслеживающий должностных обязанностей. В следующем примере создается значение необязательной определенности `Boolean` введите и объявляет переменную этого типа. Можно написать объявление тремя способами:  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]  
  
 Переменная `ridesBusToWork` может содержать значение `True`, значение `False`, или без значения. Его начальное значение по умолчанию значение не является, который в этом случае может означать, что данные не еще были получены для этого пользователя. Напротив `False` может означать, что данные были получены, и пользователь не подходите к шине для работы.  
  
 Можно объявить переменные и свойства с обнуляемые типы, и можно объявить массив, содержащий элементы типа, допускающего значение NULL. Можно объявить процедуру с типы, допускающие значения NULL в качестве параметров, и может возвращать тип nullable из `Function` процедуры.  
  
 Не удается создать тип nullable на ссылочный тип, такого как массив, `String`, или класс. Базовый тип должен быть типом значения. Для получения дополнительной информации см. [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
## <a name="using-a-nullable-type-variable"></a>С помощью переменной типа, допускающего значение NULL  
 Наиболее важные члены типа nullable являются его <xref:System.Nullable%601.HasValue%2A> и <xref:System.Nullable%601.Value%2A> свойства. Для переменной типа nullable <xref:System.Nullable%601.HasValue%2A> сообщает, содержит ли переменная определенное значение. Если <xref:System.Nullable%601.HasValue%2A> — `True`, можно считать значение из <xref:System.Nullable%601.Value%2A>. Обратите внимание, что оба <xref:System.Nullable%601.HasValue%2A> и <xref:System.Nullable%601.Value%2A> являются `ReadOnly` свойства.  
  
### <a name="default-values"></a>Значения по умолчанию  
 При объявлении переменной с типом данных допускает значения NULL, его <xref:System.Nullable%601.HasValue%2A> свойство имеет значение по умолчанию `False`. Это означает, что по умолчанию переменная не имеет определенного значения, а не значение по умолчанию значение базового типа. В следующем примере переменная `numberOfChildren` изначально не имеет заданного значения, даже если значение по умолчанию `Integer` тип равен 0.  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]  
  
 Значение null полезно для указания неопределенного или неизвестного значения. Если `numberOfChildren` был объявлен как `Integer`, будет не значение, которое может указывать, что данные не доступен.  
  
### <a name="storing-values"></a>Хранение значений  
 Сохраните значение в переменной или свойство типа nullable обычным образом. Следующий пример присваивает значение переменной `numberOfChildren` объявленные в предыдущем примере.  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]  
  
 Если переменная или свойство типа nullable содержит определенное значение, может привести к его, чтобы вернуться в исходное состояние отсутствия значение. Это можно сделать, задав переменную или свойство `Nothing`, как показано в следующем примере.  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]  
  
> [!NOTE]
>  Несмотря на то, что вы можете назначить `Nothing` переменной обнуляемого типа, но нельзя проверить ее для `Nothing` с помощью знака равенства. Сравнение, которое использует знак равенства `someVar = Nothing`, всегда равно `Nothing`. Можно проверить переменную <xref:System.Nullable%601.HasValue%2A> свойство для `False`, или проверить с помощью `Is` или `IsNot` оператор.  
  
### <a name="retrieving-values"></a>Получение значений  
 Чтобы получить значение переменной обнуляемого типа, необходимо сначала проверить ее <xref:System.Nullable%601.HasValue%2A> свойство, чтобы убедиться, что он имеет значение. Если вы пробуете читать значение при <xref:System.Nullable%601.HasValue%2A> — `False`, Visual Basic создает <xref:System.InvalidOperationException> исключение. В следующем примере показано рекомендуемый способ считать переменную `numberOfChildren` из предыдущего примера.  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]  
  
## <a name="comparing-nullable-types"></a>Сравнение обнуляемые типы  
 Если он допускает значения NULL `Boolean` переменные используются в логических выражений, в результате могут появиться `True`, `False`, или `Nothing`. Ниже приведена таблица истинности для `And` и `Or`. Так как `b1` и `b2` теперь имеют три возможных значения, существует девять комбинаций для оценки.  
  
|B1|B2|B1 и b2|B1 и b2|  
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
  
 [!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]  
  
 В этом примере `b1 And b2` принимает значение `Nothing`. В результате `Else` предложение выполняется в каждом `If` инструкции и вывод выглядит следующим образом:  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  `AndAlso` и `OrElse`, которые используют сокращенные вычисления, необходимо оценивать свои вторые операнды, если первый `Nothing`.  
  
## <a name="propagation"></a>Распространение  
 Если один или оба операнда арифметические, сравнения, shift или операции типа, допускающего значение NULL, результат операции также допускает значения NULL. Если оба операнда имеют значения, которые не `Nothing`, она выполняется на основных значениях операндов, как если бы ни были обнуляемый тип. В следующем примере переменные `compare1` и `sum1` неявно типизированы. Если навести указатель мыши над ними, вы увидите, что компилятор выводит обнуляемые типы, для них.  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]  
  
 Если один или оба операнда имеют значение `Nothing`, это приведет к появлению `Nothing`.  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]  
  
## <a name="using-nullable-types-with-data"></a>Использование допускающих значение NULL типов с данными  
 Базы данных является одним из наиболее важных знаков, используемых обнуляемых типов. Не все объекты базы данных в настоящее время поддерживает типы, допускающие значение NULL, но адаптеры таблицы, созданном конструктором. См. в разделе «Поддержка TableAdapter для обнуляемых типов» в [TableAdapter Overview](/visualstudio/data-tools/tableadapter-overview).
  
## <a name="see-also"></a>См. также

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [Использование допускающих значение NULL типов](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Общие сведения об адаптере таблиц](/visualstudio/data-tools/tableadapter-overview)
- [Оператор If](../../../../visual-basic/language-reference/operators/if-operator.md)
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md)
- [Оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md)
