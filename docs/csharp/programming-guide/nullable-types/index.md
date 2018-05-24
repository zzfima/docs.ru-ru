---
title: Типы, допускающие значения NULL (Руководство по программированию на C#)
ms.date: 05/15/2017
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: fcff492f420a60a41b373bf9042ed0c2d66d0446
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
---
# <a name="nullable-types-c-programming-guide"></a>Типы, допускающие значения NULL (Руководство по программированию на C#)
Типы, допускающие значения NULL, являются экземплярами структуры <xref:System.Nullable%601?displayProperty=nameWithType>. Тип, допускающий значение NULL, может принимать такой же диапазон значений, как и его базовый тип значения, а также дополнительное значение `null`. Например, для типа `Nullable<Int32>` (Int32, допускающий значения NULL) можно назначить любое значение в диапазоне от -2147483648 до 2147483647 или значение `null`. Тип `Nullable<bool>` может иметь значения [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md), или [null](../../../csharp/language-reference/keywords/null.md). Возможность назначения `null` для числовых и логических типов особенно полезна при работе с базами данных и другими источниками данных, которые могут содержать элементы без присвоенного значения. Например, логическое поле в базе данных может хранить значения `true` или `false`, или может быть неопределенным. 
  
[!code-csharp[nullable-types](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]  
  
Дополнительные примеры см. в разделе [Using Nullable Types (C# Programming Guide)](../../../csharp/programming-guide/nullable-types/using-nullable-types.md) (Руководство по программированию на C#. Использование типов, допускающих значение NULL)  
  
## <a name="nullable-types-overview"></a>Обзор типов, допускающих значения NULL  
 Типы, допускающие значения NULL, имеют следующие характеристики.  
  
-   Типы, допускающие значение NULL, представляют переменные типа значения, которым может быть назначено значение `null`. Нельзя создать тип, допускающий значение NULL, на основе ссылочного типа. (Ссылочные типы всегда поддерживают значение `null`.)  
  
-   Синтаксис `T?` является сокращением для <xref:System.Nullable%601>, где `T` является типом значения. Эти две формы записи являются взаимозаменяемыми.  
  
-   Типу, допускающему значение NULL, можно присвоить значение так же, как и обычному типу значения, например `int? x = 10;` или `double? d = 4.108`. Также типу, допускающему значение NULL, может быть присвоено значение `null`: `int? x = null.`.  
  
-   Используйте метод <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=nameWithType>, чтобы возвращать либо присвоенное значение, либо значение по умолчанию для базового типа, если значение равно `null`, например так: `int j = x.GetValueOrDefault();`  
  
-   Используйте доступные только для чтения свойства <xref:System.Nullable%601.HasValue%2A> и <xref:System.Nullable%601.Value%2A> для проверки на NULL и получения значения, как показано в следующем примере: `if(x.HasValue) j = x.Value;`  
  
    -   Свойство `HasValue` возвращает `true`, если переменная содержит допустимое значение, или `false`, если она имеет значение `null`.  
  
    -   Свойство `Value` возвращает значение, если оно назначено. В противном случае возникает исключение <xref:System.InvalidOperationException?displayProperty=nameWithType>.  
  
    -   По умолчанию для объекта `HasValue` установлено значение `false`. Свойство `Value` не имеет значения по умолчанию.  
  
    -   Вы также можете использовать с типом, допускающим значение NULL, операторы `==` и `!=`, как показано в следующем примере: `if (x != null) y = x;`.  
  
-   Используйте оператор `??`, чтобы назначить значение по умолчанию, которое будет применяться в том случае, если тип, допускающий значение NULL, имеет значение `null` и присваивается типу, не допускающему значение NULL (например, `int? x = null; int y = x ?? -1;`).  
  
-   Нельзя создавать вложенные типы, допускающие значение NULL. Этот код компилироваться не будет: `Nullable<Nullable<int>> n;`.  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения:  
  
-   [Использование допускающих значение NULL типов](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [Упаковка-преобразование типов, допускающих значение NULL](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [?? Оператор](../../../csharp/language-reference/operators/null-coalescing-operator.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Nullable>  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [C#](../../../csharp/index.md)  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/) (Что означает термин "расширенные"?)
