---
title: "Структуры (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# - язык, структуры"
  - "структуры [C#]"
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# Структуры (Руководство по программированию на C#)
Структуры определяются с помощью ключевого слова [struct](../../../csharp/language-reference/keywords/struct.md), например:  
  
 [!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/structs_1.cs)]  
  
 Структуры используют большую часть того же синтаксиса, что и классы, однако они более ограничены по сравнению с ними.  
  
-   В объявлении структуры поля не могут быть инициализированы до тех пор, пока они будут объявлены как постоянные или статические.  
  
-   Структура не может объявлять используемый по умолчанию конструктор \(конструктор без параметров\) или деструктор.  
  
-   Структуры копируются при присваивании.  При присваивании структуры к новой переменной выполняется копирование всех данных, а любое изменение новой копии не влияет на данные в исходной копии.  Это важно помнить при работе с коллекциями типов значений, такими как Dictionary\<string, myStruct\>.  
  
-   Структуры являются типами значений, а классы — ссылочными типами.  
  
-   В отличие то классов структуры можно создавать без использования оператора `new`.  
  
-   Структуры могут объявлять конструкторы, имеющие параметры.  
  
-   Структура не может быть унаследованной от другой структуры или класса и не может быть основой для других классов.  Все структуры наследуют непосредственно от `System.ValueType`, который наследует от `System.Object`.  
  
-   Структуры могут реализовывать интерфейсы.  
  
-   Структура может использоваться как тип, допускающий значение NULL, и ей можно назначить значение NULL.  
  
## Связанные разделы  
 Дополнительные сведения:  
  
-   [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [Практическое руководство. Определение различия между передачей структуры и ссылки класса в метод](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [Практическое руководство. Реализация определенных пользователем преобразований между структурами](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [Дополнительные сведения о переменных](http://go.microsoft.com/fwlink/?LinkId=221230) IN [Начало Visual c\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Классы](../../../csharp/programming-guide/classes-and-structs/classes.md)