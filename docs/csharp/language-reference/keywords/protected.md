---
title: "protected (справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "protected"
  - "protected_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "protected - ключевое слово [C#]"
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# protected (справочник по C#)
Ключевое слово `protected` является модификатором доступа к члену.  Доступ к члену с модификатором protected возможен внутри класса и из производных экземпляров класса.  Для сравнения ключевого слова `protected` с другими модификаторами доступа см. раздел [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md).  
  
## Пример  
 Член базового класса с модификатором protected доступен в производном классе только в том случае, если доступ осуществляется через тип производного класса.  В качестве примера рассмотрим следующий фрагмент кода:  
  
 [!code-cs[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#11)]  
  
 Оператор `a.x = 10` генерирует ошибку, поскольку он произведен внутри статического метода Main, а не внутри экземпляра класса B.  
  
 Элементы структур не могут использоваться с модификатором protected, потому что наследование от структуры невозможно.  
  
## Пример  
 В этом примере класс `DerivedPoint` является производным от класса `Point`.  Следовательно, доступ к членам базового класса с модификатором protected можно осуществлять непосредственно из производного класса.  
  
 [!code-cs[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#12)]  
  
 Если изменить уровень доступа к переменным `x` и `y` на [private](../../../csharp/language-reference/keywords/private.md), то компилятор выдаст следующие сообщения об ошибке:  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [закрытый](../../../csharp/language-reference/keywords/private.md)   
 [внутренние](../../../csharp/language-reference/keywords/internal.md)