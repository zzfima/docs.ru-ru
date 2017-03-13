---
title: "Индексаторы (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.indexers"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# - язык, индексаторы"
  - "индексаторы [C#]"
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
caps.latest.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 29
---
# Индексаторы (Руководство по программированию в C#)
Индексаторы позволяют индексировать экземпляры класса или структуры точно так же, как и массивы.  Индексаторы напоминают [свойства](../../../csharp/programming-guide/classes-and-structs/properties.md) за исключением того, что их методы доступа принимают параметры.  
  
 В следующем примере определен и предоставлен универсальный класс с простыми методами доступа [get](../../../csharp/language-reference/keywords/get.md) и [set](../../../csharp/language-reference/keywords/set.md), служащими для назначения и извлечения значений.  Класс `Program` создает экземпляр этого класса для хранения строк.  
  
 [!code-cs[csProgGuideIndexers#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/index_1.cs)]  
  
> [!NOTE]
>  Дополнительные примеры см. в разделе [Связанные разделы](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).  
  
## Определения текста выражений  
 Часто используются индексаторы, которые просто немедленно возвращаются с результатом выражения.  Для определения таких индексаторов существует сокращенный синтаксис с использованием `=>`:  
  
```c#  
public Customer this[long id] => store.LookupCustomer(id);  
  
```  
  
 Индексаторы должны быть доступны только для чтения, и вы не должны использовать ключевое слово метода доступа `get`.  
  
## Общие сведения об индексаторах  
  
-   Индексаторы позволяют индексировать объекты так же, как и массивы.  
  
-   Метод доступа `get` возвращает значение.  Метод доступа `set` назначает значение.  
  
-   Ключевое слово [this](../../../csharp/language-reference/keywords/this.md) используется для определения индексаторов.  
  
-   Ключевое слово [value](../../../csharp/language-reference/keywords/value.md) используется для определения значения, присваиваемого индексатором `set`.  
  
-   Индексаторы не нужно индексировать по целому значению; пользователь может определить конкретный механизм поиска на свое усмотрение.  
  
-   Индексаторы могут быть перегружены.  
  
-   Индексаторы могут иметь более одного формального параметра, например при доступе к двумерному массиву.  
  
##  <a name="BKMK_RelatedSections"></a> Связанные разделы  
  
-   [Использование индексаторов](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [Индексаторы в интерфейсах](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [Сравнение свойств и индексаторов](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [Ограничение доступности методов доступа](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)