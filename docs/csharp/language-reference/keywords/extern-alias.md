---
title: Псевдоним extern (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: a2803d09ee64af854cad352f6a158fb84bb6d410
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="extern-alias-c-reference"></a>Псевдоним extern (Справочник по C#)
Иногда может потребоваться сослаться на две версии сборок, которые имеют одинаковые полные имена типов. Например, если необходимо использовать две или более версии сборки в одном приложении. Используя внешний псевдоним сборки, пространства имен для каждой сборки можно перенести внутрь пространств имен корневого уровня с именованием по псевдониму, что позволяет использовать их в одном файле.  
  
> [!NOTE]
>  Ключевое слово [extern](../../../csharp/language-reference/keywords/extern.md) также используется в качестве модификатора метода, объявляющего метод, написанный в неуправляемом коде.  
  
 Для ссылки на две сборки с одинаковыми полными именами типов псевдоним необходимо указать в командной строке следующим образом:  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 При этом создаются внешние псевдонимы `GridV1` и `GridV2`. Чтобы использовать эти псевдонимы в программе, сошлитесь на них с помощью ключевого слова `extern`. Пример:  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 Каждое объявление псевдонима extern создает дополнительное пространство имен корневого уровня, которое является параллельным для глобального пространства имен (но не находится в его пределах). Таким образом, на типы из каждой сборки можно ссылаться без неоднозначности, используя их полное имя, размещенное в соответствующем пространстве имен-псевдониме.  
  
 В предыдущем примере `GridV1::Grid` является элементом управления сетки из `grid.dll`, а `GridV2::Grid` — элементом управления сетки из `grid20.dll`.  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [Оператор ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [/reference (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)
