---
title: "Типы, допускающие значения NULL (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# - язык, типы, допускающие значения NULL"
  - "типы, допускающие значения NULL [C#]"
  - "типы [C#], допускающие значения NULL"
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
caps.latest.revision: 44
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 44
---
# Типы, допускающие значения NULL (Руководство по программированию на C#)
Тип, допускающие значения NULL, являются экземплярами структуры <xref:System.Nullable%601?displayProperty=fullName>.  Тип, допускающий значения NULL, может представлять правильный диапазон значений для своего базового типа значений и дополнительное пустое значение `null`.  Например, для `Nullable<Int32>`, называемого "тип Int32, допускающий значения NULL", можно назначить любое значение от \-2 147 483 648 до 2 147 483 647 или значение `null`.  Для `Nullable<bool>` можно назначить значения [true](../../../csharp/language-reference/keywords/true.md) [false](../../../csharp/language-reference/keywords/false.md) или [null](../../../csharp/language-reference/keywords/null.md).  Возможность назначения значения `null` для числовых и логических типов особенно полезна при работе с базами данных и другими типами данных, содержащих элементы, которым может быть не назначено значение.  Например, логическое поле в базе данных может хранить значения `true` или `false` или может быть не задано.  
  
 [!code-cs[csProgGuideTypes#3](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/index_1.cs)]  
  
 Выходные данные показаны в примере:  
  
 `num = Null`  
  
 `Nullable object must have a value.`  
  
 Дополнительные примеры см. в разделе [Использование допускающих значение NULL типов](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
## Общие сведения о типах, допускающих значения NULL  
 Типы, допускающие значения NULL, имеют следующие характеристики.  
  
-   Типы, допускающие значения NULL, представляют переменные типа значения, которым можно назначать значение `null`.  Нельзя создать тип, допускающий значения NULL, на основе ссылочного типа.  \(Ссылочные типы уже поддерживают значение `null`.\)  
  
-   Синтаксис `T?` является краткой формой для <xref:System.Nullable%601>, где `T` — это тип значения.  Две эти формы взаимозаменяемы.  
  
-   Назначение значения для типа, допускающего значение null, выполняется так же, как и для обычного типа значения, например `int? x = 10;` или `double? d = 4.108`.  Типу, допускающему значение "null", также можно присваивать значение `null`: `int? x = null.`  
  
-   Используйте метод <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=fullName> для возврата назначенного значения или значения по умолчанию для базового типа, если значением является `null`, например `int j = x.GetValueOrDefault();`  
  
-   Воспользуйтесь свойствами только для чтения <xref:System.Nullable%601.HasValue%2A> и <xref:System.Nullable%601.Value%2A> для тестирования наличия значения null и извлечения значения, как показано в следующем примере: `if(x.HasValue) j = x.Value;`  
  
    -   Свойство `HasValue` возвращает `true`, если переменная содержит значение, или `false`, если оно `null`.  
  
    -   Свойство `Value` возвращает значение, если оно назначено.  В противном случае создается исключение <xref:System.InvalidOperationException?displayProperty=fullName>.  
  
    -   По умолчанию для свойства `HasValue` используется значение `false`.  Свойство `Value` не имеет значения по умолчанию.  
  
    -   С типом, допускающим значение null, можно также использовать операторы `==` и `!=`, как показано в следующем примере: `if (x != null) y = x;`  
  
-   Используйте оператор `??`, чтобы назначить значение по умолчанию, которое применяется в том случае, если тип с текущим значением `null`, допускающий значения NULL, назначен типу, не допускающему значения NULL \(например, `int? x = null; int y = x ?? -1;`\)  
  
-   Вложенные типы, допускающие значения NULL, использовать нельзя.  Компиляция следующей строки невозможна: `Nullable<Nullable<int>> n;`  
  
## Связанные разделы  
 Дополнительные сведения:  
  
-   [Использование допускающих значение NULL типов](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [Упаковка\-преобразование типов, допускающих значение NULL](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [Оператор ??](../../../csharp/language-reference/operators/null-conditional-operator.md)  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 <xref:System.Nullable>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [C\#](../../../csharp/csharp.md)   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Делает точного поднятая" средний "?](http://go.microsoft.com/fwlink/?LinkId=112382)