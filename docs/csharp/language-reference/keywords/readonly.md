---
title: "readonly (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "readonly_CSharpKeyword"
  - "readonly"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "readonly - ключевое слово [C#]"
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# readonly (Справочник по C#)
Ключевое слово `readonly` — это модификатор, который можно использовать для полей.  Если объявление поля содержит модификатор `readonly`, присвоение значений таким полям может происходить только как часть объявления или в конструкторе в том же классе.  
  
## Пример  
 Например, значение поля `year` нельзя изменить в методе `ChangeYear` несмотря на то, что в конструкторе класса ему присваивается значение:  
  
 [!code-cs[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 Можно присвоить значение полю `readonly` только в следующих контекстах:  
  
-   Когда переменная инициализируется в объявлении, например:  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   Для поля экземпляра — в конструкторах экземпляров класса, содержащего объявление поля, или, для статического поля — в статическом конструкторе класса, содержащего объявление поля.  Это единственно возможные контексты, в которых можно передавать поле `readonly` в качестве параметра [out](../../../csharp/language-reference/keywords/out.md) или [ref](../../../csharp/language-reference/keywords/ref.md).  
  
> [!NOTE]
>  Ключевое слов `readonly` отличается от ключевого слова [const](../../../csharp/language-reference/keywords/const.md).  Поле с модификатором `const` может быть инициализировано только при объявлении поля.  Поле с модификатором `readonly` может быть инициализировано при объявлении или в конструкторе.  Следовательно, поля с модификатором `readonly` могут иметь различные значения в зависимости от использованного конструктора.  Кроме того, поле `const` является константой во время компиляции, а поле `readonly` можно использовать для констант времени выполнения, как показано в следующем примере:  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## Пример  
 [!code-cs[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 В предыдущем примере при использовании такого оператора:  
  
 `p2.y = 66;        // Error`  
  
 будет отображено сообщение об ошибке компилятора:  
  
 `The left-hand side of an assignment must be an l-value`  
  
 Это такая же ошибка, которая возникает при попытке присвоить значение константе.  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [const](../../../csharp/language-reference/keywords/const.md)   
 [Поля](../../../csharp/programming-guide/classes-and-structs/fields.md)