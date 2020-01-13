---
title: Руководство по программированию на C#. Универсальные шаблоны и массивы
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
ms.openlocfilehash: a8fad38fac07b9e8d51529d3ab7070328a333dbb
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75703017"
---
# <a name="generics-and-arrays-c-programming-guide"></a>Универсальные методы и массивы (Руководство по программированию на C#)
В C# 2.0 и более поздних версиях одномерные массивы с нулевой нижней границей автоматически реализуют <xref:System.Collections.Generic.IList%601>. Это позволяет создавать универсальные методы, которые могут использовать один и тот же код для выполнения итераций в массивах и других типах коллекций. Этот способ используется преимущественно для чтения данных в коллекциях. Интерфейс <xref:System.Collections.Generic.IList%601> нельзя использовать для добавления или удаления элементов массива. При попытке вызвать метод <xref:System.Collections.Generic.IList%601>, например <xref:System.Collections.Generic.IList%601.RemoveAt%2A>, для массива в этом контексте возникнет исключение.  
  
 В следующем примере кода показано, как отдельный универсальный метод, принимающий входной параметр <xref:System.Collections.Generic.IList%601>, можно использовать для выполнения итераций в списке и массиве (в данном случае в массиве целых чисел).  
  
 [!code-csharp[csProgGuideGenerics#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#35)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Collections.Generic>
- [Руководство по программированию на C#](../index.md)
- [Универсальные шаблоны](./index.md)
- [Массивы](../arrays/index.md)
- [Универсальные шаблоны](../../../standard/generics/index.md)
