---
title: Ansi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: c7037acac58de56a396bd89f595ef897743ff4e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595083"
---
# <a name="ansi-visual-basic"></a>Ansi (Visual Basic)
Указывает, что Visual Basic должен маршалировать все строки в значения Американский национальный институт стандартов (ANSI), независимо от имени объявляемой внешней процедуры.  
  
 При вызове процедуры, определенные вне проекта, компилятор Visual Basic имеет доступ к сведениям, необходимым для корректного вызова процедуры. Эти сведения включают которой находится процедура, ее идентификатор, последовательность вызова и тип возвращаемого значения и строки кодировку. [Инструкции Declare](../../../visual-basic/language-reference/statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет необходимую информацию.  
  
 `charsetmodifier` Часть — в `Declare` оператор содержит сведения для маршалинга строк во время вызова внешней процедуры. Оно также влияет как поиска Visual Basic во внешнем файле имя внешней процедуры. `Ansi` Модификатор указывает, что Visual Basic должен маршалировать все строки в значения ANSI и должен найти процедуру без изменения имени во время поиска.  
  
 Если указан никакой модификатор набор символов, `Ansi` значение по умолчанию.  
  
## <a name="remarks"></a>Примечания  
 `Ansi` Модификатор может использоваться в этом контексте:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков интеллектуальных устройств  
 Это ключевое слово не поддерживается.  
  
## <a name="see-also"></a>См. также  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)  
 [Юникод](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
