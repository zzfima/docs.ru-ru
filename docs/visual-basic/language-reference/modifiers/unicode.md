---
title: Юникод (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
ms.openlocfilehash: a61fd8e10c39569d92dd84180f678a1ff05a9310
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="unicode-visual-basic"></a>Юникод (Visual Basic)
Указывает, что Visual Basic должен маршалировать все строки в значения Юникода независимо от имени объявляемой внешней процедуры.  
  
 При вызове процедуры, определенные вне проекта, компилятор Visual Basic имеет доступ к сведениям, необходимым для корректного вызова процедуры. Эти сведения включают которой находится процедура, ее идентификатор, последовательность вызова и тип возвращаемого значения и строки кодировку. [Инструкции Declare](../../../visual-basic/language-reference/statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет необходимую информацию.  
  
 `charsetmodifier` Часть — в `Declare` оператор содержит сведения для маршалинга строк во время вызова внешней процедуры. Оно также влияет как поиска Visual Basic во внешнем файле имя внешней процедуры. `Unicode` Модификатор указывает, что Visual Basic должен маршалировать все строки в значения Юникода и должен найти процедуру без изменения имени во время поиска.  
  
 Если указан никакой модификатор набор символов, `Ansi` значение по умолчанию.  
  
## <a name="remarks"></a>Примечания  
 `Unicode` Модификатор может использоваться в этом контексте:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков интеллектуальных устройств  
 Это ключевое слово не поддерживается.  
  
## <a name="see-also"></a>См. также  
 [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
