---
title: Оператор IsFalse (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d85fc51a75f82c65cf226b8239a8eee6585bd18a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isfalse-operator-visual-basic"></a>Оператор IsFalse (Visual Basic)
Определяет, является ли выражение `False`.  
  
 Не удается вызвать `IsFalse` явно в коде, но в Visual Basic компилятор может использовать его для создания кода из `AndAlso` предложения. Если вы задаете класса или структуры, а затем используется переменная этого типа в `AndAlso` предложение, необходимо определить `IsFalse` для этого класса или структуры.  
  
 Компилятор считает, что `IsFalse` и `IsTrue` операторы, как *соответствующие пары*. Это означает, что если определить один из них, необходимо также определить другой.  
  
> [!NOTE]
>  `IsFalse` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если его операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяется контур структуры, содержащей определения для `IsFalse` и `IsTrue` операторы.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isfalse-operator_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md)
