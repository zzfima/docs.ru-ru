---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: e8a8fb571fa65228f3a0acec1f902d21eb9bfe04
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268304"
---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Указывает, что один или несколько объявленных переменных-членов ссылаются на экземпляр класса, который может порождать события.  
  
## <a name="remarks"></a>Примечания  
 Если переменная определена с помощью `WithEvents`, декларативно, можно указать, что метод обрабатывает события переменной с помощью `Handles` ключевое слово.  
  
 Можно использовать `WithEvents` только на уровне класса или модуля. Это означает, что контекст объявления для `WithEvents` переменной должен быть классом или модуля и не может быть исходный файл, пространство имен, структуры или процедуры.  
  
 Нельзя использовать `WithEvents` для членов структуры.  
  
 Можно объявить только отдельные переменные, не массивы — с `WithEvents`.  
  
## <a name="rules"></a>Правила  
  
- **Типы элементов.** Необходимо объявить `WithEvents` переменные должны быть объектные переменные, чтобы они способны принять экземпляров класса. Тем не менее, нельзя объявлять их как `Object`. Их необходимо объявить как определенный класс, который может инициировать события.  
  
 `WithEvents` Модификатор может использоваться в этом контексте: [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
 
## <a name="example"></a>Пример

```VB
Dim WithEvents app As Application
```
  
## <a name="see-also"></a>См. также

- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [События](../../../visual-basic/programming-guide/language-features/events/index.md)
