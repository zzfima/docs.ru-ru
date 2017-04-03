---
title: "Директива using static (справочник по C#) | Документы Майкрософт"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
author: rpetrusha
ms.author: ronpet
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
ms.openlocfilehash: c072d365b4ecffb524b57c2328217da05a8af3ed
ms.lasthandoff: 03/13/2017

---
# <a name="using-static-directive-c-reference"></a>Директива using static (справочник по C#)

Директива `using static` обозначает тип, доступ к статическим членам которого можно получить, не указывая имя типа. Он имеет следующий синтаксис:

```csharp
using static <fully-qualified-type-name>
```

здесь *полное имя типа* — это имя типа, на статические члены которого можно ссылаться, не указывая имя типа. Если полное имя (полное имя пространства имен вместе с именем типа) не указано, C# создает ошибку компилятора CS0246: "Тип или пространство имен '<type-name>' не найдены".

Директива `using static` применяется к каждому типу, у которого есть статические члены, даже если при этом у него также имеются члены экземпляров. При этом для вызова членов экземпляров можно использовать только экземпляр типа.

Директива `using static` была представлена в C# версии 6.

## <a name="reamrks"></a>Примечания
 
Обычно при вызове статического члена необходимо указать имя типа и имя нужного члена. Повторный ввод одного и того же имени типа для вызова относящихся к нему элементов может сделать код слишком длинным и сложным. Например, следующее определение класса `Circle` ссылается на ряд членов класса @System.Math.
  
[!code-cs[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]

Поскольку явно ссылаться на класс @System.Math при каждой ссылке на член не требуется, директива `using static` создает гораздо более понятный код:

[!code-cs[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]

`using static` импортирует только доступные статические члены и вложенные типы, объявленные в указанном типе.  Унаследованные члены не импортируются.  Можно импортировать из любого именованного типа с помощью директивы using static, включая модули Visual Basic.  Если функции F# верхнего уровня отображаются в метаданных как статические члены именованного типа, имя которого является допустимым идентификатором C#, то эти функции F# можно импортировать.  
  
 `using static` делает методы расширения, объявленные в указанном типе, доступными для поиска метода расширения.  Тем не менее имена методов расширения не импортируются в область для неквалифицированной ссылки в коде.  
  
 Методы с тем же именем, импортированные из различных типов разными директивами `using static` в том же блоке компиляции или пространстве имен, формируют группу методов.  Разрешение перегрузки в этих группах методов соответствует обычным правилам языка C#.  
  
## <a name="example"></a>Пример

В следующем примере директива `using static` используется для того, чтобы доступ к статическим членам классов @System.Console, @System.Math и @System.String можно было получать, не указывая имя типа.

[!code-cs[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]

В этом примере директива `using static` может также применяться к типу @System.Double. В этом случае вызвать метод @System.Double.TryParse(System.String,System.Double@), не указав имя типа, было бы невозможно. При этом код становится менее понятным, поскольку появляется необходимость проверять операторы `using static` и определять, какой метод числового типа `TryParse` вызывается.

## <a name="see-also"></a>См. также

[Директива using](using-directive.md)   
[Справочник по C#](../../../csharp/language-reference/index.md)   
[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
[Использование пространств имен](../../../csharp/programming-guide/namespaces/using-namespaces.md)   
[Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md)   
[Пространства имен](../../../csharp/programming-guide/namespaces/index.md)   

