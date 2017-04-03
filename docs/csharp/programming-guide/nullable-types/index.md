---
title: "Типы, допускающие значение NULL (руководство по программированию на C#) | Документация Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
caps.latest.revision: 44
author: BillWagner
ms.author: wiwagn
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 75726b9864abc0c9b556085e5215c6692d80fb12
ms.lasthandoff: 03/13/2017

---
# <a name="nullable-types-c-programming-guide"></a>Типы, допускающие значения NULL (Руководство по программированию на C#)
Все типы, допускающие значение NULL, являются экземплярами структуры <xref:System.Nullable%601?displayProperty=fullName>. Тип, допускающий значение NULL, может принимать такой же диапазон значений, как и его базовый тип значения, а также дополнительное значение `null`. Например, для типа `Nullable<Int32>` (Int32, допускающий значения NULL) можно назначить любое значение в диапазоне от -2147483648 до 2147483647 или значение `null`. Тип `Nullable<bool>` может иметь значения [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md), или [null](../../../csharp/language-reference/keywords/null.md). Возможность назначения `null` для числовых и логических типов особенно полезна при работе с базами данных и другими источниками данных, которые могут содержать элементы без присвоенного значения. Например, логическое поле в базе данных может хранить значения `true` или `false`, или может быть неопределенным.  
  
 [!code-cs[csProgGuideTypes#3](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/index_1.cs)]  
  
 Этот пример кода отображает такие выходные данные:  
  
 `num = Null`  
  
 `Nullable object must have a value.`  
  
 Дополнительные примеры см. в разделе [Using Nullable Types (C# Programming Guide)](../../../csharp/programming-guide/nullable-types/using-nullable-types.md) (Руководство по программированию на C#. Использование типов, допускающих значение NULL)  
  
## <a name="nullable-types-overview"></a>Обзор типов, допускающих значения NULL  
 Типы, допускающие значения NULL, имеют следующие характеристики.  
  
-   Типы, допускающие значение NULL, представляют переменные типа значения, которым может быть назначено значение `null`. Нельзя создать тип, допускающий значение NULL, на основе ссылочного типа. (Ссылочные типы всегда поддерживают значение `null`.)  
  
-   Синтаксис `T?` является сокращением для <xref:System.Nullable%601>, где `T` является типом значения. Эти две формы записи являются взаимозаменяемыми.  
  
-   Типу, допускающему значение NULL, можно присвоить значение так же, как и обычному типу значения, например `int? x = 10;` или `double? d = 4.108`. Также типу, допускающему значение NULL, может быть присвоено значение `null`: `int? x = null.`.  
  
-   Используйте метод <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=fullName>, чтобы возвращать присвоенное значение или значение по умолчанию для базового типа, если значение равно `null`, например так: `int j = x.GetValueOrDefault();`.  
  
-   Используйте свойства <xref:System.Nullable%601.HasValue%2A> и <xref:System.Nullable%601.Value%2A>, доступные только для чтения, чтобы проверить наличие значения NULL и получить значение, как показано в следующем примере: `if(x.HasValue) j = x.Value;`.  
  
    -   Свойство `HasValue` возвращает `true`, если переменная содержит допустимое значение, или `false`, если она имеет значение `null`.  
  
    -   Свойство `Value` возвращает значение, если оно назначено. В противном случае создается исключение <xref:System.InvalidOperationException?displayProperty=fullName>.  
  
    -   По умолчанию для объекта `HasValue` установлено значение `false`. Свойство `Value` не имеет значения по умолчанию.  
  
    -   Вы также можете использовать с типом, допускающим значение NULL, операторы `==` и `!=`, как показано в следующем примере: `if (x != null) y = x;`.  
  
-   Используйте оператор `??`, чтобы назначить значение по умолчанию, которое будет применяться в том случае, если тип, допускающий значение NULL, имеет значение `null` и присваивается типу, не допускающему значение NULL (например, `int? x = null; int y = x ?? -1;`).  
  
-   Нельзя создавать вложенные типы, допускающие значение NULL. Этот код компилироваться не будет: `Nullable<Nullable<int>> n;`.  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения:  
  
-   [Использование допускающих значение NULL типов](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [Упаковка-преобразование типов, допускающих значение NULL](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [?? Оператор](../../../csharp/language-reference/operators/null-conditional-operator.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Nullable>   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [C#](../../../csharp/csharp.md)   
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [What exactly does 'lifted' mean?](http://go.microsoft.com/fwlink/?LinkId=112382) (Что означает термин "расширенные"?)

