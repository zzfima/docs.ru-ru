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
ms.openlocfilehash: 98dafab3e524ea371bba228eb231e28d46cc3b4e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819459"
---
# <a name="ansi-visual-basic"></a>Ansi (Visual Basic)
Указывает, что Visual Basic должен маршалировать все строки в Американский национальный институт стандартов (ANSI) независимо от имени объявляемой внешней процедуры.  
  
 При вызове процедуры, определенные вне проекта, компилятор Visual Basic имеет доступ к сведениям, необходимым для корректного вызова процедуры. Эти сведения включают местонахождения процедуры, ее идентификатор, его последовательность вызова и тип возвращаемого значения и строки кодировку. [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет необходимую информацию.  
  
 `charsetmodifier` В `Declare` оператор содержит сведения для маршалинга строк во время вызова внешней процедуры. Оно также влияет, как Visual Basic выполняет внешнем файле имя внешней процедуры. `Ansi` Модификатор указывает, что Visual Basic должен маршалировать все строки в значения ANSI и должен найти процедуру без изменения имени во время поиска.  
  
 Если указан никакой модификатор набора символов, `Ansi` используется по умолчанию.  
  
## <a name="remarks"></a>Примечания  
 `Ansi` Модификатор может использоваться в этом контексте:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков смарт-устройств  
 Это ключевое слово не поддерживается.  
  
## <a name="see-also"></a>См. также

- [Auto](../../../visual-basic/language-reference/modifiers/auto.md)
- [Юникод](../../../visual-basic/language-reference/modifiers/unicode.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
