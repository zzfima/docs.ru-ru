---
title: Когда следует использовать перечисление (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: a43c55d4ad6a895957b53ae18c3641c5383a24ce
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64585078"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a>Когда следует использовать перечисление (Visual Basic)
Перечисления предоставляют простой способ работы с наборами связанных констант. Перечисление или `Enum`, является символическое имя для набора значений. Перечисления обрабатываются как типы данных и их можно использовать для создания наборов констант для использования с переменными и свойства.  
  
## <a name="when-to-use-an-enumeration"></a>Когда следует использовать перечисление  
 Когда процедура принимает ограниченный набор переменных, следует использовать перечисление. Перечисление делает код более удобочитаемым, особенно в том случае, если используются значимые имена.  
  
 Преимущества использования перечисления:  
  
- Сокращает число ошибок, вызванных перемещением или неправильным вводом значений.  
  
- Позволяет легко изменять значения в будущем.  
  
- Делает код более удобным для чтения, это означает, что это снижает вероятность возникновения ошибок в нем.  
  
- Обеспечение прямой совместимости. С помощью перечисления код является менее вероятны ошибки, если в будущем кто-то изменяет значения, соответствующие именам элементов.  
  
## <a name="naming-enumerations"></a>Именование перечислений  
 Используйте соглашения об именовании для членов перечисления. Когда Visual Basic встречает имя члена перечисления, может быть исключение если тем же именем содержится в других библиотеках типов. Используйте уникальный префикс, который определяет значения из своего приложения или компонента.  
  
 При ссылке на член перечисления, вам необходимо уточнить имя члена перечисления или воспользуйтесь `Imports` инструкции. Дополнительные сведения см. в разделе [перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## <a name="predefined-enumerations"></a>Предопределенные перечисления  
 Visual Basic предоставляет ряд стандартных перечислений, таких как `FirstDayOfWeek` и `MsgBoxResult`, для упрощения кода. Список кодов см. в разделе [константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Объявления перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Практическое руководство. Ссылка на член перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Практическое руководство. Перебор элементов перечисления в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Практическое руководство. Определение строки, связанной со значением из перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Оператор Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
