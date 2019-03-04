---
title: Как выполнить Руководство по программированию на C#. Использование словаря для хранения экземпляров событий
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: f3b8e313bd0b1bd3973102caebb9bbc9da620ae6
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203036"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Использование словаря для хранения экземпляров событий
`accessor-declarations` можно применять для предоставления большого числа событий таким образом, что вместо отдельного поля для каждого события будет использоваться словарь для хранения экземпляров событий. Такой подход эффективен только в том случае, если у вас будет большое число событий, большинство из которых не будет реализовано.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [События](../../../csharp/programming-guide/events/index.md)
- [Делегаты](../../../csharp/programming-guide/delegates/index.md)
