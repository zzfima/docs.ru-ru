---
title: Auto (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1e32c4c910567829a4f5c59b48020db4dfbbeb7b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="auto-visual-basic"></a>Auto (Visual Basic)
Указывает, что Visual Basic должен маршалировать строки в соответствии с правилами .NET Framework на основе внешнего имени объявляемой внешней процедуры.  
  
 При вызове процедуры, определенные вне проекта, компилятор Visual Basic имеет доступ к сведениям, необходимым для корректного вызова процедуры. Эти сведения включают которой находится процедура, ее идентификатор, последовательность вызова и тип возвращаемого значения и строки кодировку. [Инструкции Declare](../../../visual-basic/language-reference/statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет необходимую информацию.  
  
 `charsetmodifier` Часть — в `Declare` оператор содержит сведения для маршалинга строк во время вызова внешней процедуры. Оно также влияет как поиска Visual Basic во внешнем файле имя внешней процедуры. `Auto` Модификатор указывает, что Visual Basic должен маршалировать строки в соответствии с правилами .NET Framework, его следует определить базовый кодировки платформы во время выполнения и, возможно, изменить имя внешней процедуры начального поиска не выполняется. Дополнительные сведения см. в разделе «Наборы символов» в [инструкции Declare](../../../visual-basic/language-reference/statements/declare-statement.md).  
  
 Если указан никакой модификатор набор символов, `Ansi` значение по умолчанию.  
  
## <a name="remarks"></a>Примечания  
 `Auto` Модификатор может использоваться в этом контексте:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков интеллектуальных устройств  
 Это ключевое слово не поддерживается.  
  
## <a name="see-also"></a>См. также  
 [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [Юникод](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
