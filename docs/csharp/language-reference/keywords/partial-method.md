---
title: "разделяемый (метод) (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- partialmethod_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
caps.latest.revision: 26
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
ms.openlocfilehash: b6f8ecca01ebf681c906b73abefc94e9e45b8700
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="partial-method-c-reference"></a>разделяемый (метод) (Справочник по C#)
Сигнатура разделяемого метода определяется в одной части разделяемого типа, а его реализация — в другой части этого типа. С помощью разделяемых методов разработчики классов могут при необходимости реализовывать ловушки методов, которые схожи с обработчиками событий. Если реализация не предоставлена, компилятор удаляет сигнатуру во время компиляции. В отношении разделяемых методов применяются следующие условия:  
  
-   Сигнатуры в обеих частях разделяемого типа должны совпадать.  
  
-   Метод должен возвращать значение void.  
  
-   Модификаторы доступа не допускаются. Разделяемые методы являются неявно частными.  
  
 В следующем примере показан разделяемый метод, определенный в двух частях разделяемого класса:  
  
 [!code-cs[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]  
  
 Дополнительные сведения см. в разделе [Разделяемые классы и методы](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [partial (тип)](../../../csharp/language-reference/keywords/partial-type.md)

