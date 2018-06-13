---
title: Недопустимое соглашение о вызовах DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: d8c7f7aea46162215115689305f4010cb513b020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583842"
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
