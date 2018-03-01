---
title: "interface (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aba9ee66a90216066a47f22e251182caad465818
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="interface-c-reference"></a>interface (Справочник по C#)
Интерфейс содержит только сигнатуры [методов](../../../csharp/programming-guide/classes-and-structs/methods.md), [свойств](../../../csharp/programming-guide/classes-and-structs/properties.md), [событий](../../../csharp/programming-guide/events/index.md) или [индексаторов](../../../csharp/programming-guide/indexers/index.md). Класс или структура, реализующие интерфейс, должны реализовать члены интерфейса, заданные в определении интерфейса. В следующем примере класс `ImplementationClass` должен реализовать метод с именем `SampleMethod`, не имеющий параметров и возвращающий значение `void`.  
  
 Дополнительные сведения и примеры см. в разделе [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]  
  
 Интерфейс может быть членом пространства имен или класса и содержать сигнатуры следующих членов:  
  
-   [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [Свойства](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [Индексаторы](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [События](../../../csharp/language-reference/keywords/event.md)  
  
 Интерфейс может наследовать от одного или нескольких базовых интерфейсов.  
  
 Если список базовых типов содержит базовый класс и интерфейсы, базовый класс должен стоять первым в списке.  
  
 Класс, реализующий интерфейс, может явно реализовывать члены этого интерфейса. При явной реализации члена к нему можно получить доступ только через экземпляр интерфейса, но не через экземпляр класса.  
  
 Дополнительные сведения и примеры кода с явной реализацией интерфейса см. в разделе [Явная реализация интерфейса](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показана реализация интерфейса. В этом примере интерфейс содержит объявление свойства, а класс содержит реализацию. Любой экземпляр класса, который реализует `IPoint`, имеет целочисленные свойства `x` и `y`.  
  
 [!code-csharp[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md)  
 [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md)  
 [Использование свойств](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
 [Использование индексаторов](../../../csharp/programming-guide/indexers/using-indexers.md)  
 [class](../../../csharp/language-reference/keywords/class.md)  
 [struct](../../../csharp/language-reference/keywords/struct.md)  
 [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md)
