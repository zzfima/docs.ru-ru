---
title: Когда следует использовать перечисление
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: 5daae8d487ddfe079a54e305e59e32e8ded8f65e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353963"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a>Когда следует использовать перечисление (Visual Basic)
Перечисления предлагают простой способ работы с наборами связанных констант. Перечисление, или `Enum`, является символическим именем для набора значений. Перечисления обрабатываются как типы данных, и их можно использовать для создания наборов констант для использования с переменными и свойствами.  
  
## <a name="when-to-use-an-enumeration"></a>Когда следует использовать перечисление  
 Если процедура принимает ограниченный набор переменных, рекомендуется использовать перечисление. Перечисления делают более понятным и удобочитаемым кодом, особенно при использовании осмысленных имен.  
  
 Ниже перечислены преимущества использования перечислений.  
  
- Сокращает количество ошибок, вызванных перечислением или неотрицательным вводом чисел.  
  
- Упрощает изменение значений в будущем.  
  
- Упрощает чтение кода. Это означает, что менее вероятно, что ошибки будут отменяться.  
  
- Обеспечивает прямую совместимость. При использовании перечислений код менее вероятен, если в будущем кто-то изменит значения, соответствующие именам элементов.  
  
## <a name="naming-enumerations"></a>Перечисления именования  
 Используйте соглашение об именовании для членов перечисления. Когда Visual Basic встречает имя члена перечисления, может возникнуть исключение, если другие библиотеки типов содержат одно и то же имя. Используйте уникальный префикс, определяющий значения из приложения или компонента.  
  
 При ссылке на член перечисления необходимо уточнить имя члена с помощью имени перечисления или использовать оператор `Imports`. Дополнительные сведения см. в разделе [перечисления и квалификация имени](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## <a name="predefined-enumerations"></a>Предопределенные перечисления  
 Visual Basic предоставляет ряд предопределенных перечислений, таких как `FirstDayOfWeek` и `MsgBoxResult`, для упрощения кода. Список этих элементов см. в разделе [константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## <a name="see-also"></a>См. также

- [Инструкции. Объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Практическое руководство. Ссылка на элемент перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Пошаговое руководство. перебор перечислений в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Практическое руководство. Определение строки, связанной со значением из перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Оператор Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
