---
title: "private (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "private_CSharpKeyword"
  - "private"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "private - ключевое слово [C#]"
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# private (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевое слово `private` является модификатором доступа к члену.  Закрытый \(private\) доступ является уровнем доступа с минимальными правами.  Доступ к закрытым членам можно получить только внутри тела класса или структуры, в которой они объявлены, как показано в следующем примере:  
  
```  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  
  
 Вложенные типы в том же теле могут также обращаться к таким закрытым членам.  
  
 Ошибка времени компиляции возникнет в том случае, если создать ссылку на закрытый член за пределами класса или структуры, в которой он объявлен.  
  
 Сравнение модификатора `private` с другими модификаторами доступа см. в разделах [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) и [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
## Пример  
 В этом примере класс `Employee` содержит два закрытых элемента данных – `name` и `salary`.  Как к закрытым членам, к ним нельзя получить доступ кроме как через методы членов.  Для получения управляемого доступа к закрытым членам можно использовать методы с именем `GetName` и `Salary`.  Доступ к методу `name` можно получить через открытый метод, а к методу `salary` – через открытое свойство только для чтения.  \(Дополнительные сведения см. в разделе [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md).\)  
  
 [!code-cs[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [защищенные](../../../csharp/language-reference/keywords/protected.md)   
 [внутренние](../../../csharp/language-reference/keywords/internal.md)