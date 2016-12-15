---
title: "const (Справочник по C#) | Microsoft Docs"
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
  - "const_CSharpKeyword"
  - "const"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "const - ключевое слово [C#]"
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
caps.latest.revision: 28
caps.handback.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# const (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Для объявления константного поля или константной локальной используется ключевое слово `const`.  Константные поля и локальные не являются переменными и не могут быть изменены.  Константы могут быть числами, логическими значениями, строками или нулевыми ссылками.  Не создавайте константу для предоставления сведений, которые могут измениться в любое время.  Например, не используйте константное поле для хранения цены услуги, номера версии продукта или торгового названия компании.  Эти значения могут со временем измениться, а поскольку константы распространяются компиляторами, для отражения изменений потребуется повторная компиляция остальных кодов, скомпилированных с использованием ваших библиотек.  См. также ключевое слово [readonly](../../../csharp/language-reference/keywords/readonly.md).  Например:  
  
```  
  
      const int x = 0;  
public const double gravitationalConstant = 6.673e-11;  
private const string productName = "Visual C#";  
```  
  
## Заметки  
 Тип объявления константы указывает на тип членов, которые вводятся объявлением.  Инициализатор константной локальной или константного поля должен быть выражением константы, поддерживающим явное преобразование в конечный тип.  
  
 Выражение константы — это выражение, которое можно полностью оценить во время компиляции.  Таким образом, единственно возможными значениями для констант типов ссылок являются `string` и нулевые ссылки.  
  
 Объявление константы может объявлять несколько констант, например:  
  
```  
public const double x = 1.0, y = 2.0, z = 3.0;  
```  
  
 Модификатор `static` в объявлении константы не допускается.  
  
 Константа может участвовать в выражении константы следующим образом:  
  
```  
public const int c1 = 5;  
public const int c2 = c1 + 100;  
```  
  
> [!NOTE]
>  Ключевое слово [readonly](../../../csharp/language-reference/keywords/readonly.md) отличается от ключевого слова `const`.  Поле `const` может быть инициализировано только при объявлении поля.  Поле `readonly` может быть инициализировано при объявлении или в конструкторе.  Таким образом, поля `readonly` могут иметь разные значения в зависимости от использованного конструктора.  Также, несмотря на то, что поле `const` является константой во время компиляции, поле `readonly` можно использовать для констант во время выполнения, как в следующей строке: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`  
  
## Пример  
 [!code-cs[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]  
  
## Пример  
 В этом примере показан способ использования констант в качестве локальных переменных.  
  
 [!code-cs[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [readonly](../../../csharp/language-reference/keywords/readonly.md)