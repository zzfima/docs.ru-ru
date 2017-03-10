---
title: "public (справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "public"
  - "public_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "public - ключевое слово [C#]"
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# public (справочник по C#)
Ключевое слово `public` является модификатором доступа для типов и членов типов.  Общий \(public\) доступ является уровнем доступа с максимальными правами.  Ограничений доступа к общим членам не существует, как показано в следующем примере:  
  
```  
class SampleClass  
{  
    public int x; // No access restrictions.  
}  
```  
  
 Дополнительные сведения см. в разделах [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) и [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md).  
  
## Пример  
 В следующем примере объявляются два класса: `PointTest` и `MainClass`.  Доступ к общим членам `x` и `y` класса `PointTest` осуществляется непосредственно из класса `MainClass`.  
  
 [!code-cs[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#13)]  
  
 Если уровень доступа `public` изменить на [private](../../../csharp/language-reference/keywords/private.md) или [protected](../../../csharp/language-reference/keywords/protected.md), то в результате будет выводиться следующее сообщение об ошибке:  
  
 Доступ к элементу "PointTest.y" невозможен из\-за его уровня защиты.  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [закрытый](../../../csharp/language-reference/keywords/private.md)   
 [защищенные](../../../csharp/language-reference/keywords/protected.md)   
 [внутренние](../../../csharp/language-reference/keywords/internal.md)