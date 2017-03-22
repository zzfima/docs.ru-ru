---
title: "WithEvents (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.WithEvents
- WithEvents
dev_langs:
- VB
helpviewer_keywords:
- WithEvents keyword
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 708cf6fec78faf2c7a5959a3a2694d237d728882
ms.lasthandoff: 03/13/2017

---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Указывает, что один или несколько переменных объявленного члена относится к экземпляру класса, который может порождать события.  
  
## <a name="remarks"></a>Примечания  
 Если переменная определена с помощью `WithEvents`, можно декларативно указать, что метод обрабатывает события переменной с помощью `Handles` ключевое слово.  
  
 Можно использовать `WithEvents` только на уровне класса или модуля. Это означает, что контекст объявления для `WithEvents` переменной должен быть классом или модулем и не может быть исходным файлом, пространство имен, структуры или процедуры.  
  
 Нельзя использовать `WithEvents` для членов структуры.  
  
 Можно объявлять только отдельные переменные — не массивы — с `WithEvents`.  
  
## <a name="rules"></a>Правила  
  
-   **Типы элементов.** Необходимо объявить `WithEvents` переменные объектные переменные, что позволяет им принимать экземпляры классов. Однако нельзя объявлять их как `Object`. Их необходимо объявить как определенный класс, который может инициировать события.  
  
 `WithEvents` Модификатор может использоваться в этом контексте: [в операторе Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>См. также  
 [Обрабатывает](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)   
 [События](../../../visual-basic/programming-guide/language-features/events/index.md)
