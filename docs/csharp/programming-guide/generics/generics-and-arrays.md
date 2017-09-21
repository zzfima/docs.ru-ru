---
title: "Универсальные методы и массивы (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 46cea2733504e56aec5e65a4c9a8b655bc9431cf
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-arrays-c-programming-guide"></a>Универсальные методы и массивы (Руководство по программированию на C#)
В C# 2.0 и более поздних версиях одномерные массивы с нулевой нижней границей автоматически реализуют <xref:System.Collections.Generic.IList%601>. Это позволяет создавать универсальные методы, которые могут использовать один и тот же код для выполнения итераций в массивах и других типах коллекций. Этот способ используется преимущественно для чтения данных в коллекциях. Интерфейс <xref:System.Collections.Generic.IList%601> нельзя использовать для добавления или удаления элементов массива. При попытке вызвать метод <xref:System.Collections.Generic.IList%601>, например <xref:System.Collections.Generic.IList%601.RemoveAt%2A>, для массива в этом контексте возникнет исключение.  
  
 В следующем примере кода показано, как отдельный универсальный метод, принимающий входной параметр <xref:System.Collections.Generic.IList%601>, можно использовать для выполнения итераций в списке и массиве (в данном случае в массиве целых чисел).  
  
 [!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Generic>   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Универсальные шаблоны](~/docs/standard/generics/index.md)

