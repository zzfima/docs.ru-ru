---
title: Недопустимое соглашение о вызовах DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: f7b0c3a6edbe0b950195306fa66287ff9b209bfe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935282"
---
# <a name="bad-dll-calling-convention"></a>Недопустимое соглашение о вызовах DLL
Аргументы, переданные в библиотеку динамической компоновки (DLL) должна в точности совпадать с ожидается подпрограммой. Соглашения о вызовах содержат число, тип и порядок аргументов. Программа вызывает подпрограммы в библиотеку DLL, передан неправильный тип или количество аргументов.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Убедитесь, что все типы аргументов совпадают с теми, которые указаны в объявлении процедуры, что при вызове.  
  
2. Убедитесь, что вы передаете одинаковое количество аргументов, указанным в объявлении процедуры, который вы вызываете.  
  
3. Если программы DLL ожидает передачи аргументов по значению, убедитесь, что `ByVal` указан для этих аргументов в объявлении.  
  
## <a name="see-also"></a>См. также

- [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Оператор Call](../../../visual-basic/language-reference/statements/call-statement.md)
- [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
