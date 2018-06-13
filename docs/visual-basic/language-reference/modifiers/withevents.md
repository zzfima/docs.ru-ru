---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 240058a534456ae20c9c129a068bae575ac45eda
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596012"
---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Указывает, что один или несколько объявленных переменных-членов относятся к экземпляру класса, который может порождать события.  
  
## <a name="remarks"></a>Примечания  
 Если переменная определена с помощью `WithEvents`, декларативно, можно указать, что метод обрабатывает события переменной с помощью `Handles` ключевое слово.  
  
 Можно использовать `WithEvents` только на уровне класса или модуля. Это означает, что контекст объявления для `WithEvents` переменной должен быть классом или модулем и не может быть исходным файлом, пространство имен, структуры или процедуры.  
  
 Нельзя использовать `WithEvents` для членов структуры.  
  
 Можно объявить только отдельные переменные — не массивы — с `WithEvents`.  
  
## <a name="rules"></a>Правила  
  
-   **Типы элементов.** Необходимо объявить `WithEvents` переменные объектные переменные, чтобы они могут принимать экземпляры классов. Однако нельзя объявлять их в виде `Object`. Их необходимо объявить как определенный класс, который может инициировать события.  
  
 `WithEvents` Модификатор может использоваться в этом контексте: [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>См. также  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)  
 [События](../../../visual-basic/programming-guide/language-features/events/index.md)
