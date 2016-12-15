---
title: "is (Справочник по C#) | Microsoft Docs"
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
  - "is_CSharpKeyword"
  - "is"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "is - ключевое слово [C#]"
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# is (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Проверяет совместимость объекта с заданным типом.  Например, в следующем коде определяется, является ли объект экземпляром типа `MyObject` или типа, производного от `MyObject`:  
  
```  
if (obj is MyObject)  
{  
}  
```  
  
 Если предоставленное выражение отлично от NULL и предоставленный объект может быть приведен к предоставленному типу не вызывая исключение, выражение `is` принимает значение `true`.  
  
 Ключевое слово `is` вызывает предупреждение во время компиляции, если известно, что выражение всегда будет иметь значение `true` или `false`, однако обычно оценивает совместимость типов во время выполнения.  
  
 Оператор `is` перегрузить нельзя.  
  
 Обратите внимание, что оператор `is` рассматривает только преобразование ссылок, упаковки\-преобразования и распаковки\-преобразования.  Другие преобразования, например определенные пользователем, не учитываются.  
  
 Анонимные методы не разрешены с левой стороны оператора `is`.  К этому исключению относятся лямбда\-выражения.  
  
## Пример  
 [!code-cs[csrefKeywordsOperator#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/is_1.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [typeof](../../../csharp/language-reference/keywords/typeof.md)   
 [as](../../../csharp/language-reference/keywords/as.md)   
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)