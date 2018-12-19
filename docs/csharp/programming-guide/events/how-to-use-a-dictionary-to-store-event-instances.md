---
title: Как выполнить Руководство по программированию на C#. Использование словаря для хранения экземпляров событий
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: 819c81aed3a6f09a20e51285058dcc77749dd33a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245146"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Использование словаря для хранения экземпляров событий
`accessor-declarations` можно применять для предоставления большого числа событий таким образом, что вместо отдельного поля для каждого события будет использоваться словарь для хранения экземпляров событий. Такой подход эффективен только в том случае, если у вас будет большое число событий, большинство из которых не будет реализовано.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [События](../../../csharp/programming-guide/events/index.md)  
- [Делегаты](../../../csharp/programming-guide/delegates/index.md)
