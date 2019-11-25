---
title: Руководство по программированию на C#. Типы перечислений
ms.custom: seodec18
ms.date: 09/10/2017
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
ms.openlocfilehash: 3573959a1e10b475a9867631767de5d10a08b9ea
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73969766"
---
# <a name="enumeration-types-c-programming-guide"></a>Типы перечислений (Руководство по программированию в C#)

Тип перечисления (называемый также перечислением) предоставляет эффективный способ определения набора именованных целочисленных констант, который можно назначить переменной. Например, предположим, что нужно определить переменную, значение которого должно представлять день недели. Имеется только семь имеющих смысл значений, которые может принимать переменная. Для определения этих значений можно использовать тип перечисления, который объявлен с помощью ключевого слова [enum](../language-reference/keywords/enum.md).

[!code-csharp[csProgGuideEnums#1](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#1)]

По умолчанию базовым типом каждого элемента перечисления является [int](../language-reference/builtin-types/integral-numeric-types.md). Можно задать другой целочисленный тип, используя двоеточие, как показано в предыдущем примере. Полный список возможных типов см. в разделе [enum (справочник по C#)](../language-reference/keywords/enum.md).

Чтобы проверить основные числовые значения путем приведения в базовый тип, как показано в следующем примере.

```csharp
Day today = Day.Monday;
int dayNumber =(int)today;
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);

Month thisMonth = Month.Dec;
byte monthNumber = (byte)thisMonth;
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);

// Output:
// Monday is day number #1.
// Dec is month number #11.
```

Далее указаны преимущества использования enum вместо числового типа.

- Для клиентского кода ясно задается, какие значения допустимы для переменной.

- В Visual Studio IntelliSense выводит список определенных значений.

Если не указать значения этих элементов в списке перечислителя, значения будут автоматически увеличиваться на 1. В предыдущем примере `Day.Sunday` имеет значение 0, `Day.Monday` имеет значение 1 и т. д. Когда создается новый объект `Day`, он будет иметь значение по умолчанию `Day.Sunday` (0), только ему явно не присвоить значение. При создании перечисления выберите наиболее логичное используемое по умолчанию значение и присвойте ему значение нуль. В результате этого все перечисления, если при их создании им явно не задать значение, будут иметь по умолчанию это значение.

Если переменная `meetingDay` имеет тип `Day`, ей можно (без явного приведения) присвоить только одно из значений, определенных в `Day`. И если день встречи изменяется, можно назначить новое значение из `Day` переменной `meetingDay`:

[!code-csharp[csProgGuideEnums#4](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#4)]

> [!NOTE]
> Переменной `meetingDay` можно присвоить любое произвольное целое значение. Например, эта строка кода не создает ошибку: `meetingDay = (Day) 42`. Но этого делать нельзя, поскольку неявно ожидается, что переменная перечисления принимает одно из значений, определяемых перечислением. Присвоение переменной типа перечисления произвольного значения связано с большим риском возникновения ошибок.

Элементам списка перечислителя типа перечисления можно присвоить любые значения, и можно также использовать вычисленные значения:

[!code-csharp[csProgGuideEnums#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#3)]

## <a name="enumeration-types-as-bit-flags"></a>Типы перечислений как битовые флаги

Тип перечисления можно использовать для определения битовых флагов, благодаря чему экземпляр типа перечисления может хранить любую комбинацию значений, определенных в списке перечислителя. (Конечно, некоторые комбинации могут не иметь смысла или быть недопустимы в коде программы.)

Чтобы создать перечисление битовых флагов, нужно применить атрибут <xref:System.FlagsAttribute?displayProperty=nameWithType> и определить значения так, чтобы для них могли выполняться битовые операции `AND`, `OR`, `NOT` и `XOR`. В перечисление битовых флагов включите именованную константу с нулевым значением, что означает "флаги не установлены". Не придавайте флагу нулевое значение, если оно не означает "флаги не установлены".

В следующем примере определена другая версия перечисления `Day`, которая называется `Days`. У `Days` имеется атрибут `Flags`, и каждому значению присваивается следующая степень числа 2. Это позволяет создать переменную `Days` со значением `Days.Tuesday | Days.Thursday`.

[!code-csharp[csProgGuideEnums#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#2)]

Чтобы установить флаг на перечислении, используйте побитовый оператор `OR`, как показано в следующем примере:

[!code-csharp[csProgGuideEnums#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#6)]

Чтобы определить, установлен ли конкретный флаг, используйте побитовый оператор `AND`, как показано в следующем примере:

[!code-csharp[csProgGuideEnums#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#7)]

Дополнительные сведения о том, что необходимо учитывать при определении типов перечислений при помощи атрибута <xref:System.FlagsAttribute?displayProperty=nameWithType>, см. в статье <xref:System.Enum?displayProperty=nameWithType>.

## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a>Использование методов System.Enum для получения и обработки значений перечисления

Все перечисления являются экземплярами типа <xref:System.Enum?displayProperty=nameWithType>. Нельзя унаследовать новые классы от класса <xref:System.Enum?displayProperty=nameWithType>, но можно использовать его методы для получения и изменения данных об экземпляре перечисления.

[!code-csharp[csProgGuideEnums#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#5)]

Дополнительные сведения можно найти по адресу: <xref:System.Enum?displayProperty=nameWithType>.

Можно также создать для перечисления новый метод, используя метод расширения. Дополнительные сведения см. в разделе [Практическое руководство. Создание нового метода для перечисления](./classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).

## <a name="see-also"></a>См. также

- <xref:System.Enum?displayProperty=nameWithType>
- [Руководство по программированию на C#](./index.md)
- [enum](../language-reference/keywords/enum.md)
