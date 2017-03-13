---
title: "interface (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "interface_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "interface - ключевое слово [C#]"
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
caps.latest.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 29
---
# interface (Справочник по C#)
Интерфейс содержит только сигнатуры [методов](../../../csharp/programming-guide/classes-and-structs/methods.md), [свойств](../../../csharp/programming-guide/classes-and-structs/properties.md), [событий](../../../csharp/programming-guide/events/index.md) или [индексаторов](../../../csharp/programming-guide/indexers/index.md).  Класс или структура, которые реализуют интерфейс, должны реализовать члены этого интерфейса, указанные в его определении.  В следующем примере класс `ImplementationClass` должен реализовать метод с именем `SampleMethod` , который не имеет параметров и возвращает `void`.  
  
 Дополнительные сведения и примеры см. в разделе [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md).  
  
## Пример  
 [!code-cs[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]  
  
 Интерфейс может быть членом пространства имен или класса и содержать подписи следующих членов:  
  
-   [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [Свойства](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [Indexers](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [События](../../../csharp/language-reference/keywords/event.md)  
  
 Интерфейс способен наследовать от одного или нескольких базовых интерфейсов.  
  
 Если в списке базовых типов содержится базовый класс и интерфейсы, то базовый класс должен стоять в списке на первом месте.  
  
 Класс, реализующий интерфейс, может явным образом реализовывать члены этого интерфейса.  Явно реализованный член можно вызвать только через экземпляр интерфейса, но не через экземпляр класса.  
  
 Дополнительные сведения и примеры кода с явной реализацией интерфейса см. в разделе [Явная реализация интерфейса](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).  
  
## Пример  
 В следующем примере демонстрируется реализация интерфейса.  В этом примере интерфейс содержит объявление свойства, а класс содержит реализацию.  Любой экземпляр класса, реализующего `IPoint`, имеет целочисленные свойства `x` и `y`.  
  
 [!code-cs[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md)   
 [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md)   
 [Использование свойств](../../../csharp/programming-guide/classes-and-structs/using-properties.md)   
 [Использование индексаторов](../../../csharp/programming-guide/indexers/using-indexers.md)   
 [класс](../../../csharp/language-reference/keywords/class.md)   
 [struct](../../../csharp/language-reference/keywords/struct.md)   
 [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md)