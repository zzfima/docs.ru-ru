---
title: Ansi
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: 0c38c2b81af7b4cb8fd1723853a09c5413f805af
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344738"
---
# <a name="ansi-visual-basic"></a>Ansi (Visual Basic)
Указывает, что Visual Basic должны маршалировать все строки в значения Американский национальный институт стандартов (ANSI) (ANSI) независимо от имени объявляемой внешней процедуры.  
  
 При вызове процедуры, определенной вне проекта, Visual Basic компилятор не имеет доступа к информации, которая необходима для правильного вызова процедуры. Эти сведения включают в себя расположение процедуры, способ ее определения, последовательность вызова и тип возвращаемого значения, а также используемую строковую кодировку. [Инструкция DECLARE](../../../visual-basic/language-reference/statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет эти необходимые сведения.  
  
 `charsetmodifier` часть в инструкции `Declare` предоставляет сведения о кодировке для упаковки строк во время вызова внешней процедуры. Он также влияет на то, как Visual Basic ищет имя внешней процедуры во внешнем файле. Модификатор `Ansi` указывает, что Visual Basic должен маршалировать все строки в значения ANSI и выполнять поиск процедуры, не изменяя ее имя во время поиска.  
  
 Если модификатор кодировки не указан, по умолчанию используется `Ansi`.  
  
## <a name="remarks"></a>Заметки  
 Модификатор `Ansi` можно использовать в этом контексте:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков смарт-устройств  
 Это ключевое слово не поддерживается.  
  
## <a name="see-also"></a>См. также

- [Auto](../../../visual-basic/language-reference/modifiers/auto.md)
- [Юникод](../../../visual-basic/language-reference/modifiers/unicode.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
