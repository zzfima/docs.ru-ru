---
title: Auto (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: c128ab9982ae7ccd5fff34020f2750f703da16a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664607"
---
# <a name="auto-visual-basic"></a>Auto (Visual Basic)
Указывает, что Visual Basic должен маршалировать строки в соответствии с правилами .NET Framework, на основе внешнего имени объявляемой внешней процедуры.  
  
 При вызове процедуры, определенные вне проекта, компилятор Visual Basic имеет доступ к сведениям, необходимым для корректного вызова процедуры. Эти сведения включают местонахождения процедуры, ее идентификатор, его последовательность вызова и тип возвращаемого значения и строки кодировку. [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет необходимую информацию.  
  
 `charsetmodifier` В `Declare` оператор содержит сведения для маршалинга строк во время вызова внешней процедуры. Оно также влияет, как Visual Basic выполняет внешнем файле имя внешней процедуры. `Auto` Модификатор указывает, что Visual Basic должен маршалировать строки в соответствии с правилами .NET Framework, его следует определить базовый кодировки среды выполнения платформы и, возможно, изменить имя внешней процедуры, если начальный поиск происходит сбой. Дополнительные сведения см. в разделе «Наборы символов» в [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).  
  
 Если указан никакой модификатор набора символов, `Ansi` используется по умолчанию.  
  
## <a name="remarks"></a>Примечания  
 `Auto` Модификатор может использоваться в этом контексте:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков смарт-устройств  
 Это ключевое слово не поддерживается.  
  
## <a name="see-also"></a>См. также
- [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)
- [Юникод](../../../visual-basic/language-reference/modifiers/unicode.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
