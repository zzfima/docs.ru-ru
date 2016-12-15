---
title: "Псевдоним extern (Справочник по C#) | Microsoft Docs"
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
  - "alias_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "псевдонимы [C#], extern - ключевое слово"
  - "псевдонимы, extern - ключевое слово"
  - "extern - ключевое слово псевдонима [C#]"
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Псевдоним extern (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В некоторых случаях может потребоваться задать ссылки на две версии сборок с одинаковыми полными именами типов.  Например, вам необходимо использовать две или более версий сборки в одном приложении.  С помощью внешнего псевдонима сборки можно включить пространства имен для каждой сборки в оболочку внутри пространств имен корневого уровня, именуемых по этому псевдониму, что позволяет использовать их в одном файле.  
  
> [!NOTE]
>  Ключевое слово [extern](../../../csharp/language-reference/keywords/extern.md) также используется в качестве модификатора метода, объявляющего метод, написанный в неуправляемом коде.  
  
 Чтобы ссылаться на две сборки с помощью одинаковых полных имен типов, псевдоним должен быть указан в командной строке следующим образом:  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 Здесь создаются внешние псевдонимы `GridV1` и `GridV2`.  Чтобы использовать эти псевдонимы в программе, создайте на них ссылку с помощью ключевого слова `extern`.  Примеры.  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 При каждом объявлении псевдонима extern вводится дополнительное пространство имен корневого уровня, которое соответствует глобальному пространству имен \(но не находится внутри него\).  Таким образом ссылки на типы из каждой сборки без неоднозначности могут создаваться с помощью их полного имени, корнем которого является соответствующий псевдоним пространства имен.  
  
 В предыдущем пример `GridV1::Grid` — это элемент управления Grid из `grid.dll`, а `GridV2::Grid` — это элемент управления Grid из `grid20.dll`.  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [Оператор ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [\/reference \(Import Metadata\)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)