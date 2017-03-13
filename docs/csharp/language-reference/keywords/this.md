---
title: "this (Справочник по C#) | Microsoft Docs"
description: this keyword (C# Reference)
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "this"
  - "this_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "this - ключевое слово [C#]"
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# this (Справочник по C#)
Ключевое слово `this` ссылается на текущий экземпляр класса, а также используется в качестве модификатора первого параметра метода расширения.  
  
> [!NOTE]
>  В этой статье рассматривается использование `this` с экземплярами класса.  Дополнительные сведения об использовании этого ключевого слова в методах расширения см. в разделе [Методы расширения](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
 Ниже перечислены наиболее частые способы использования `this`.  
  
-   Для квалификации элементов, скрытых одинаковыми именами, например:  
  
 [!code-cs[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]  
  
-   Для передачи другим методам объекта в качестве параметра, например:  
  
    ```  
    CalcTax(this);  
    ```  
  
-   Для объявления индексаторов, например:  
  
 [!code-cs[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]  
  
 У статических функций\-членов нет указателя `this`, так как они существуют только на уровне класса и не являются частями объектов.  Использование ссылки на `this` в статическом методе является недопустимым.  
  
## Пример  
 В этом примере `this` используется для квалификации членов класса `Employee`, `name` и `alias`, которые скрыты одинаковыми именами.  Также это ключевое слово используется для передачи объекта в метод `CalcTax`, который принадлежит к другому классу.  
  
 [!code-cs[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [базовые](../../../csharp/language-reference/keywords/base.md)   
 [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)