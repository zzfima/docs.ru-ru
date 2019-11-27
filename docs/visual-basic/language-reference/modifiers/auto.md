---
title: Auto
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: 7ea46e5f8b882bb986f23e792b240bad0c5be7a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351621"
---
# <a name="auto-visual-basic"></a>Auto (Visual Basic)
Указывает, что Visual Basic должны маршалировать строки согласно правилам .NET Framework, исходя из внешнего имени объявляемой внешней процедуры.  
  
 При вызове процедуры, определенной вне проекта, Visual Basic компилятор не имеет доступа к информации, которая необходима для правильного вызова процедуры. Эти сведения включают в себя расположение процедуры, способ ее определения, последовательность вызова и тип возвращаемого значения, а также используемую строковую кодировку. [Инструкция DECLARE](../../../visual-basic/language-reference/statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет эти необходимые сведения.  
  
 `charsetmodifier` часть в инструкции `Declare` предоставляет сведения о кодировке для упаковки строк во время вызова внешней процедуры. Он также влияет на то, как Visual Basic ищет имя внешней процедуры во внешнем файле. Модификатор `Auto` указывает, что Visual Basic должен маршалировать строки в соответствии с правилами .NET Framework и определить базовый набор символов платформы времени выполнения и, возможно, изменить имя внешней процедуры в случае сбоя первоначального поиска. Дополнительные сведения см. в разделе «Наборы символов» в [операторе Declare](../../../visual-basic/language-reference/statements/declare-statement.md).  
  
 Если модификатор кодировки не указан, по умолчанию используется `Ansi`.  
  
## <a name="remarks"></a>Примечания  
 Модификатор `Auto` можно использовать в этом контексте:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков смарт-устройств  
 Это ключевое слово не поддерживается.  
  
## <a name="see-also"></a>См. также

- [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)
- [Юникод](../../../visual-basic/language-reference/modifiers/unicode.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
