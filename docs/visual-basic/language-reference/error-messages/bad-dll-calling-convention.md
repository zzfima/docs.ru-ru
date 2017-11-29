---
title: "Недопустимое соглашение о вызовах DLL"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: daa84e82d2fbe1041af56fdd5cc3855efd814ddf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="bad-dll-calling-convention"></a>Недопустимое соглашение о вызовах DLL
Аргументы, передаваемые в библиотеке динамической компоновки (DLL) должна в точности совпадать с ожидаемый подпрограммы. Соглашения о вызовах содержат число, тип и порядок аргументов. Программа вызывает другую программу в DLL, которая передается неправильный тип или количество аргументов.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что все типы аргументов совпадают с теми, которые указаны в объявлении процедуры, который вы вызываете.  
  
2.  Убедитесь, что вы передаете одинаковое количество аргументов, указанным в объявлении процедуры, что вы работаете.  
  
3.  Если программы DLL ожидает передачи аргументов по значению, убедитесь, что `ByVal` указан для этих аргументов в объявлении процедуры.  
  
## <a name="see-also"></a>См. также  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [Оператор Call](../../../visual-basic/language-reference/statements/call-statement.md)  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
