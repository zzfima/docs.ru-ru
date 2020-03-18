---
title: Руководство по программированию на C#. Универсальные методы
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], methods
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
ms.openlocfilehash: 5f066ca39c97b70554886e423c37c4ee47d49158
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712199"
---
# <a name="generic-methods-c-programming-guide"></a>Универсальные методы (Руководство по программированию на C#)
Универсальным называется метод, объявленный с использованием параметров типа, как показано ниже:  
  
 [!code-csharp[csProgGuideGenerics#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#22)]  
  
 В следующем примере кода показан один из способов вызова метода с использованием `int` в качестве аргумента типа:  
  
 [!code-csharp[csProgGuideGenerics#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#23)]  
  
 Если опустить аргумент типа, компилятор определит его. Следующий вызов `Swap` эквивалентен предыдущему:  
  
 [!code-csharp[csProgGuideGenerics#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#24)]  
  
 Для статических методов и методов экземпляра применяются одинаковые правила определения типа. Компилятор может определить параметры типа на основе переданных ему аргументов метода. Определение параметров типа невозможно только для ограничения или возвращаемого значения. Соответственно, механизм определения типа не работает с методами, не имеющими параметров. Определение типа происходит во время компиляции до того, как компилятор попытается разрешить сигнатуры перегруженных методов. Компилятор применяет логику определения типа ко всем универсальным методам с одинаковым именем. На этапе разрешения перегрузки компилятор включает только те универсальные методы, для которых был успешно определен тип.  
  
 В универсальном классе методы, не являющиеся универсальными, могут получать доступ к параметрам типа на уровне класса следующим образом:  
  
 [!code-csharp[csProgGuideGenerics#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#25)]  
  
 Если определить универсальный метод, принимающий те же параметры типа, что и содержащий его класс, возникнет предупреждение компилятора [CS0693](../../misc/cs0693.md). Это связано с тем, что в области действия метода предоставленный для внутреннего типа `T` аргумент скрывает аргумент, предоставленный для внешнего типа `T`. Для большей гибкости можно вызывать метод универсального класса с использованием аргументов типа, отличающихся от предоставленных при создании экземпляра класса. В этом случае следует предоставить другой идентификатор для параметра типа метода, как показано в `GenericList2<T>` в следующем примере.  
  
 [!code-csharp[csProgGuideGenerics#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#26)]  
  
 С помощью ограничений можно реализовать специализированные операции в отношении параметров типа в методах. Эта версия `Swap<T>` теперь называется `SwapIfGreater<T>` и может использоваться только с типами, реализующими <xref:System.IComparable%601>.  
  
 [!code-csharp[csProgGuideGenerics#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#27)]  
  
 Универсальные методы могут быть перегружены в нескольких параметрах типа. Например, все представленные ниже методы могут располагаться в одном классе:  
  
 [!code-csharp[csProgGuideGenerics#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#28)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 Дополнительные сведения см. в [спецификации языка C#](~/_csharplang/spec/classes.md#methods).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Collections.Generic>
- [Руководство по программированию на C#](../index.md)
- [Введение в универсальные шаблоны](./index.md)
- [Методы](../classes-and-structs/methods.md)
