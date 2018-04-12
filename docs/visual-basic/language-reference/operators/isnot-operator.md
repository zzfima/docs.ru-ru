---
title: Оператор IsNot (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 969fdebdf15a1f779075c58616ccd16c64976a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isnot-operator-visual-basic"></a>Оператор IsNot (Visual Basic)
Сравнивает две переменные объектной ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Значение `Boolean`.  
  
 `object1`  
 Обязательный. Любой `Object` переменной или выражения.  
  
 `object2`  
 Обязательный. Любой `Object` переменной или выражения.  
  
## <a name="remarks"></a>Примечания  
 `IsNot` Оператор определяет, если две объектные ссылки на разные объекты. Однако сравнение значений не выполняется. Если `object1` и `object2` ссылаются на точное же экземпляр объекта, `result` — `False`; в противном случае, `result` — `True`.  
  
 `IsNot`шаблон противоположен `Is` оператор. Преимущество `IsNot` — избегать неуклюжим синтаксису `Not` и `Is`, который может быть трудно читать.  
  
 Можно использовать `Is` и `IsNot` операторы для проверки объектов с ранним связыванием и поздним связыванием.  
  
> [!NOTE]
>  `IsNot` Оператор не может использоваться для сравнения выражений, возвращенных `TypeOf` оператор. Вместо этого необходимо использовать `Not` и `Is` операторы.  
  
## <a name="example"></a>Пример  
 В следующем примере кода используются `Is` оператор и `IsNot` оператор для выполнения того же сравнения.  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Is](../../../visual-basic/language-reference/operators/is-operator.md)  
 [Оператор TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Практическое руководство. Проверка совпадения двух объектов](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
