---
title: Типы значений, допускающие значение NULL
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
ms.openlocfilehash: beed8262c50dc68330b8f03aa3d864ed2f8df0d5
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249686"
---
# <a name="nullable-value-types-visual-basic"></a>Типы значения, допускающие Null (Visual Basic)

Иногда вы работаете с типом значения, который не имеет определенного значения в определенных обстоятельствах. Например, поле в базе данных может иметь различие между наличием значимого значения и не имеющим назначенного значения. Типы значений могут быть расширены, чтобы взять либо их нормальные значения, либо нулевое значение. Такое расширение называется *недействительным типом.*

Каждый недействительный тип значения <xref:System.Nullable%601> построен из общей структуры. Рассмотрим базу данных, которая отслеживает действия, связанные с работой. Следующий пример строит недействительный `Boolean` тип и объявляет переменную этого типа. Заявление можно написать тремя способами:

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

Переменная `ridesBusToWork` может содержать `True`значение, `False`значение, или нет значения вообще. Его начальное значение по умолчанию не является значением вообще, что в этом случае может означать, что информация еще не была получена для этого человека. В отличие `False` от этого, может означать, что информация была получена, и человек не едет на автобусе на работу.

Вы можете декларировать переменные и свойства с необыдательными типами значений, а также объявлять массив с элементами необдуманного типа значения. В качестве параметров можно объявить процедуры с необыдаными типами значений, а также вернуть из `Function` процедуры несоизглаенный тип значения.

Вы не можете построить недействительный тип на `String`типе ссылки, например массив, a или класс. Базовым типом должен быть тип значения. Для получения дополнительной информации [см.](value-types-and-reference-types.md)

## <a name="using-a-nullable-type-variable"></a>Использование переменной nullable Типа

Наиболее важными членами несоизлучаемого типа значения являются его <xref:System.Nullable%601.HasValue%2A> свойства и <xref:System.Nullable%601.Value%2A> свойства. Для переменной необнутивной тип <xref:System.Nullable%601.HasValue%2A> значения, показывает, содержит ли переменная определенное значение. Если <xref:System.Nullable%601.HasValue%2A> `True`это, вы можете <xref:System.Nullable%601.Value%2A>прочитать значение от . Обратите внимание, <xref:System.Nullable%601.Value%2A> `ReadOnly` что оба <xref:System.Nullable%601.HasValue%2A> свойства и являются свойствами.

### <a name="default-values"></a>Значения по умолчанию

Когда вы объявляете переменную с необыдательным типом значения, ее <xref:System.Nullable%601.HasValue%2A> свойство имеет значение по `False`умолчанию. Это означает, что по умолчанию переменная не имеет определенного значения, а не значение по умолчанию своего базового типа значения. В следующем примере `numberOfChildren` переменная изначально не имеет определенного значения, даже если значение `Integer` типа по умолчанию составляет 0.

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

Нулевое значение полезно для обозначения неопределенного или неизвестного значения. Если `numberOfChildren` бы было `Integer`объявлено, не было бы значения, которое могло бы указывать на то, что информация в настоящее время недоступна.

### <a name="storing-values"></a>Хранение ценностей

Вы храните значение в переменной или свойстве нулевого типа значения типичным способом. Следующий пример присваивает `numberOfChildren` значение переменной, заявленной в предыдущем примере.

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

Если переменная или свойство нулевого типа значения содержит определенное значение, вы можете заставить ее вернуться к исходному состоянию, не имеющего значения, назначенного. Вы делаете это, устанавливая `Nothing`переменную или свойство, как показано в следующем примере.

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> Хотя вы можете `Nothing` назначить переменную нулевого типа значения, `Nothing` вы не можете проверить его с помощью равного знака. Сравнение, которое `someVar = Nothing`использует равный `Nothing`знак, всегда оценивает . Вы <xref:System.Nullable%601.HasValue%2A> можете проверить свойство `False`переменной для, `Is` или `IsNot` проверить с помощью оператора.

### <a name="retrieving-values"></a>Получение значений

Чтобы получить значение переменной нулевой типа значения, необходимо сначала <xref:System.Nullable%601.HasValue%2A> проверить ее свойство, чтобы подтвердить, что она имеет значение. Если вы попытаетесь <xref:System.Nullable%601.HasValue%2A> прочитать значение, когда это, `False`Visual Basic бросает <xref:System.InvalidOperationException> исключение. Ниже приводится рекомендуемый способ чтения `numberOfChildren` переменной предыдущих примеров.

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a>Сравнение недействительных типов

Когда недействительные `Boolean` переменные используются в выражениях `True`Boolean, результат может быть, `False`или `Nothing`. Ниже приведена таблица `And` `Or`правды для и . Потому что `b1` и `b2` теперь есть три возможных значения, Есть девять комбинаций для оценки.

|b1|B2|b1 И b2|b1 Или b2|
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

Когда значение переменной Boolean или `Nothing`выражения, `true` это `false`не является ни . Рассмотрим следующий пример.

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

В этом `b1 And b2` примере `Nothing`оценивается. В результате `Else` положение выполняется в `If` каждом заявлении, и вывод следующий:

`Expression is not true`

`Expression is not false`

> [!NOTE]
> `AndAlso`и `OrElse`, которые используют оценку короткого замыкания, должны оценить `Nothing`свои вторые оперы, когда первый оценивает .

## <a name="propagation"></a>Распространение

Если одна или обе операции арифметики, сравнения, переноса или типа являются необоснованной типом значения, результат операции также является необоснованной типом значения. Если оба операции имеют значения, которые `Nothing`не являются, операция выполняется на основных значениях operands, как если бы ни один из них не был необоснованного типа значения. В следующем примере `compare1` переменные и `sum1` неявно набраны. Если вы полежите указателем мыши над ними, вы увидите, что компилятор вычеркивает недействительные типы значений для обоих из них.

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

Если один или оба operands `Nothing`имеют значение, `Nothing`результат будет .

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a>Использование недействительных типов с данными

База данных является одним из наиболее важных мест для использования недействительных типов значений. В настоящее время не все объекты базы данных поддерживают необнудаемые типы значений, но адаптеры таблиц, созданные дизайнером, поддерживаются. Смотрите [поддержку TableAdapter для недействительных типов.](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types)

## <a name="see-also"></a>См. также

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [Типы данных](index.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Устранение неполадок, связанных с типами данных](troubleshooting-data-types.md)
- [Заполнение наборов данных с помощью адаптеров таблицы](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [Оператор If](../../../language-reference/operators/if-operator.md)
- [Вывод локального типа](../variables/local-type-inference.md)
- [Оператор Is](../../../language-reference/operators/is-operator.md)
- [Оператор IsNot](../../../language-reference/operators/isnot-operator.md)
- [Недействительные типы значений (C)](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
