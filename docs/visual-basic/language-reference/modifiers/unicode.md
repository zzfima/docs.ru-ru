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
ms.openlocfilehash: 491bbb24be8e6a3044b0a433c5ad262596ae00d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655287"
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
