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
ms.openlocfilehash: b3c9452f8d144fb18ea3efcb35b85caed80e8692
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778681"
---
# <a name="unicode-visual-basic"></a>Юникод (Visual Basic)
Указывает, что Visual Basic должен маршалировать все строки в значениях Юникод независимо от имени объявляемой внешней процедуры.  
  
 При вызове процедуры, определенные вне проекта, компилятор Visual Basic имеет доступ к сведениям, необходимым для корректного вызова процедуры. Эти сведения включают местонахождения процедуры, ее идентификатор, его последовательность вызова и тип возвращаемого значения и строки кодировку. [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет необходимую информацию.  
  
 `charsetmodifier` В `Declare` оператор содержит сведения для маршалинга строк во время вызова внешней процедуры. Оно также влияет, как Visual Basic выполняет внешнем файле имя внешней процедуры. `Unicode` Модификатор указывает, что Visual Basic должен маршалировать все строки в значениях Юникод и должен найти процедуру без изменения имени во время поиска.  
  
 Если указан никакой модификатор набора символов, `Ansi` используется по умолчанию.  
  
## <a name="remarks"></a>Примечания  
 `Unicode` Модификатор может использоваться в этом контексте:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков смарт-устройств  
 Это ключевое слово не поддерживается.  
  
## <a name="see-also"></a>См. также

- [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)
- [Auto](../../../visual-basic/language-reference/modifiers/auto.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
