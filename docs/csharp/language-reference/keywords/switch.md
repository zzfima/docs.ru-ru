---
title: "switch (Справочник по C#) | Microsoft Docs"
ms.date: "2017-03-07"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "switch_CSharpKeyword"
  - "switch"
  - "case"
  - "case_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "switch - оператор [C#]"
  - "switch - ключевое слово [C#]"
  - "case - оператор [C#]"
  - "default - ключевое слово [C#]"
ms.assetid: 44bae8b8-8841-4d85-826b-8a94277daecb
caps.latest.revision: 47
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 47
---
# switch (Справочник по C#)
Выражение `switch` — это оператор управления, выбирающий *раздел switch* для выполнения из списка кандидатов.  
  
 Оператор `switch` включает один или несколько разделов switch.  Каждый раздел switch содержит одну или несколько *меток case*, за которыми следует один или несколько операторов.  В следующем примере показан простой оператор `switch` с тремя разделами switch.  Каждый раздел switch содержит одну метку case, например `case 1`, и два оператора.  
  
 [!code-cs[csrefKeywordsSelection#7](../../../csharp/language-reference/keywords/codesnippet/csharp/switch_1.cs)]  
  
## Заметки  
 В каждой метке case указывается постоянное значение.  Оператор switch передает управление тому разделу, метка case которого совпадает со значением *выражение switch* \(`caseSwitch` в этом примере\).  Если метка case не содержит соответствующего значения, управление передается в раздел `default`, если таковой имеется.  Если раздела `default` нет, никакие действия не выполняются и управление передается за пределы оператора `switch`.  В предыдущем примере, выполняются операторы в первом разделе switch, поскольку `case 1` совпадает со значением `caseSwitch`.  
  
 Оператор `switch` может содержать любое количество разделов switch, а каждый раздел может иметь одну или несколько меток case \(как показано в этом примере ниже\).  Однако две метки case не могут содержать одно и то же постоянное значение.  
  
 Выполнение списка операторов в выбранном разделе switch начинается с первого оператора и продолжается по списку, обычно до достижения оператора перехода, такого как `break`, `goto case`, `return` или `throw`.  В этой точке управление передается за пределы оператора `switch` или к другой метке case.  
  
 В отличие от C\+\+, C\# не позволяет продолжить выполнение следующего раздела switch после выполнения предыдущего раздела.  Приведенный ниже код вызывает ошибку.  
  
```c#  
switch (caseSwitch)  
{  
    // The following switch section causes an error.  
    case 1:  
        Console.WriteLine("Case 1...");  
        // Add a break or other jump statement here.  
    case 2:  
        Console.WriteLine("... and/or Case 2");  
        break;  
}  
```  
  
 Согласно требованиям C\# конец разделов switch, включая последний раздел, должен быть недостижим.  То есть, в отличие от некоторых языков, выполнение не может переходить на следующий раздел switch.  Хотя это требование обычно выполняется с помощью оператора `break`, допустим также следующий вариант, поскольку он гарантирует, что конец списка операторов не будет достигнут.  
  
```c#  
case 4:  
    while (true)  
        Console.WriteLine("Endless looping. . . .");  
```  
  
## Пример  
 В следующем примере показаны требования и возможности оператора `switch`.  
  
 [!code-cs[csrefKeywordsSelection#9](../../../csharp/language-reference/keywords/codesnippet/csharp/switch_2.cs)]  
  
## Пример  
 В последнем случае поток выполнения контролируется строковой переменной `str` и строковыми метками case.  
  
 [!code-cs[csrefKeywordsSelection#8](../../../csharp/language-reference/keywords/codesnippet/csharp/switch_3.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Оператор switch \(C\+\+\)](/visual-cpp/cpp/switch-statement-cpp)   
 [if\-else](../../../csharp/language-reference/keywords/if-else.md)