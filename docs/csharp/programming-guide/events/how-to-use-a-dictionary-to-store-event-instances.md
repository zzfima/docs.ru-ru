---
title: Практическое руководство. Использование словаря для хранения экземпляров событий (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: 97a7b0f168e4a1c81ec396f42b731dabb45b3516
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33327220"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>Практическое руководство. Использование словаря для хранения экземпляров событий (Руководство по программированию в C#)
`accessor-declarations` можно применять для предоставления большого числа событий таким образом, что вместо отдельного поля для каждого события будет использоваться словарь для хранения экземпляров событий. Такой подход эффективен только в том случае, если у вас будет большое число событий, большинство из которых не будет реализовано.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [События](../../../csharp/programming-guide/events/index.md)  
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)
