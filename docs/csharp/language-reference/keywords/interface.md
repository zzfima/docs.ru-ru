---
title: "interface (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- interface_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
caps.latest.revision: 29
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
ms.openlocfilehash: 84759153ebfc77ba6d39e1b3c47a00a083f267c0
ms.lasthandoff: 03/13/2017

---
# <a name="interface-c-reference"></a>interface (Справочник по C#)
Интерфейс содержит только сигнатуры [методов](../../../csharp/programming-guide/classes-and-structs/methods.md), [свойств](../../../csharp/programming-guide/classes-and-structs/properties.md), [событий](../../../csharp/programming-guide/events/index.md) или [индексаторов](../../../csharp/programming-guide/indexers/index.md). Класс или структура, реализующие интерфейс, должны реализовать члены интерфейса, заданные в определении интерфейса. В следующем примере класс `ImplementationClass` должен реализовать метод с именем `SampleMethod`, не имеющий параметров и возвращающий значение `void`.  
  
 Дополнительные сведения и примеры см. в разделе [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md).  
  
## <a name="example"></a>Пример  
 [!code-cs[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]  
  
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
  
 [!code-cs[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
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
