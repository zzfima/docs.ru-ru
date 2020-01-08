---
title: Типы значения, допускающие Null
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
ms.openlocfilehash: 0d259e11a969f4eb7e64626a4adf498db06ece06
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347841"
---
# <a name="nullable-value-types-visual-basic"></a>Типы значения, допускающие Null (Visual Basic)

Иногда вы работаете с типом значения, который не имеет определенного значения в определенных обстоятельствах. Например, поле в базе данных может отличаться от присвоенного значения, которое является осмысленным и не имеет присвоенного значения. Типы значений могут быть расширены для получения их нормальных значений или значения NULL. Такое расширение называется *типом, допускающим значение NULL*.

Каждый допускающий значение NULL тип создается из универсальной структуры <xref:System.Nullable%601>. Рассмотрим базу данных, которая отслеживает действия, связанные с работой. В следующем примере создается тип `Boolean` Nullable и объявляется переменная этого типа. Объявление можно написать тремя способами:

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

Переменная `ridesBusToWork` может содержать значение `True`, значение `False`или вообще не имеет значения. Его начальное значение по умолчанию — вообще не имеет значения, что в данном случае может означать, что данные еще не были получены для этого пользователя. В отличие от этого, `False` может означать, что информация была получена, и пользователь не перейдет на шину.

Можно объявить переменные и свойства с типами, допускающими значение null, и можно объявить массив с элементами типа, допускающего значение null. В качестве параметров можно объявить процедуры с типами, допускающими значение null, и можно вернуть тип, допускающий значение null, из процедуры `Function`.

Нельзя создать тип, допускающий значение null, для ссылочного типа, такого как массив, `String`или класс. Базовый тип должен быть типом значения. Для получения дополнительной информации см. [Value Types and Reference Types](value-types-and-reference-types.md).

## <a name="using-a-nullable-type-variable"></a>Использование переменной типа, допускающей значение null

Наиболее важными членами типа, допускающего значение null, являются свойства <xref:System.Nullable%601.HasValue%2A> и <xref:System.Nullable%601.Value%2A>. Для переменной типа, допускающего значение null, <xref:System.Nullable%601.HasValue%2A> сообщает, содержит ли переменная определенное значение. Если <xref:System.Nullable%601.HasValue%2A> `True`, можно прочитать значение из <xref:System.Nullable%601.Value%2A>. Обратите внимание, что свойства <xref:System.Nullable%601.HasValue%2A> и <xref:System.Nullable%601.Value%2A> `ReadOnly`.

### <a name="default-values"></a>Значения по умолчанию

При объявлении переменной с типом, допускающим значение null, ее свойство <xref:System.Nullable%601.HasValue%2A> имеет значение по умолчанию `False`. Это означает, что по умолчанию переменная не имеет определенного значения, а не значения по умолчанию базового типа значения. В следующем примере переменная `numberOfChildren` изначально не имеет определенного значения, несмотря на то, что значение по умолчанию для типа `Integer` равно 0.

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

Значение NULL полезно для указания неопределенного или неизвестного значения. Если `numberOfChildren` было объявлено как `Integer`, то не будет значения, которое могло бы означать, что информация в настоящее время недоступна.

### <a name="storing-values"></a>Сохранение значений

Вы сохраняете значение в переменной или свойстве типа, допускающего значение null, обычным способом. В следующем примере значение присваивается переменной, `numberOfChildren` объявленной в предыдущем примере.

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

Если переменная или свойство типа, допускающего значение null, содержит определенное значение, можно вернуть его первоначальное состояние, не имеющее присвоенного значения. Для этого нужно задать для переменной или свойства значение `Nothing`, как показано в следующем примере.

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> Хотя можно присвоить `Nothing` переменной типа, допускающего значение null, ее нельзя протестировать для `Nothing` с помощью знака равенства. При сравнении, в котором используется знак равенства, `someVar = Nothing`, всегда вычисляется `Nothing`. Можно проверить свойство <xref:System.Nullable%601.HasValue%2A> переменной для `False`или проверить с помощью оператора `Is` или `IsNot`.

### <a name="retrieving-values"></a>Получение значений

Чтобы получить значение переменной типа, допускающего значение null, сначала следует проверить его свойство <xref:System.Nullable%601.HasValue%2A>, чтобы убедиться, что оно имеет значение. Если попытаться считать значение, когда <xref:System.Nullable%601.HasValue%2A> `False`, Visual Basic выдаст исключение <xref:System.InvalidOperationException>. В следующем примере показан рекомендуемый способ чтения переменной `numberOfChildren` из предыдущих примеров.

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a>Сравнение типов, допускающих значение null

Если в логических выражениях используются значения NULL `Boolean` переменные, результат может быть `True`, `False`или `Nothing`. Ниже приведена таблица истинности для `And` и `Or`. Поскольку `b1` и `b2` теперь имеют три возможных значения, можно вычислить девять комбинаций.

|B1|ячейк|B1 и B2|B1 или B2|
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

Если значение логической переменной или выражения `Nothing`, оно не является ни `true`, ни `false`. Рассмотрим следующий пример.

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

В этом примере `b1 And b2` вычисляется как `Nothing`. В результате предложение `Else` выполняется в каждой инструкции `If`, и выходные данные выглядят следующим образом:

`Expression is not true`

`Expression is not false`

> [!NOTE]
> `AndAlso` и `OrElse`, которые используют сокращенную оценку, должны оценивать свои вторые операнды, когда первый вычисляется как `Nothing`.

## <a name="propagation"></a>Распространение

Если один или оба операнда арифметических операций, операции сравнения, сдвига или типа допускают значение null, результат операции также может допускать значение null. Если оба операнда имеют значения, которые не `Nothing`, операция выполняется с базовыми значениями операндов, как если бы ни был тип, допускающий значение null. В следующем примере переменные `compare1` и `sum1` неявно типизированы. Если навести на них указатель мыши, вы увидите, что компилятор выводит типы, допускающие значение null, для обоих типов.

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

Если один или оба операнда имеют значение `Nothing`, результат будет `Nothing`.

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a>Использование типов, допускающих значение null, с данными

База данных является одним из наиболее важных мест для использования типов, допускающих значение null. Не все объекты базы данных в настоящее время поддерживают типы, допускающие значение null, но адаптеры таблиц, созданные конструктором, выполняют. См. раздел [Поддержка TableAdapter для типов, допускающих значение NULL](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).

## <a name="see-also"></a>См. также:

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [Типы данных](index.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Устранение неполадок, связанных с типами данных](troubleshooting-data-types.md)
- [Заполнение наборов данных с помощью адаптера таблицы](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [Оператор If](../../../language-reference/operators/if-operator.md)
- [Вывод локального типа](../variables/local-type-inference.md)
- [Оператор Is](../../../language-reference/operators/is-operator.md)
- [Оператор IsNot](../../../language-reference/operators/isnot-operator.md)
- [Типы значений, допускающие значение null (C#)](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
