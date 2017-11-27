---
title: "Когда следует использовать перечисление (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a3b2937cc71c0c31bd8dce3d77fb33f48e1b5750
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-use-an-enumeration-visual-basic"></a>Когда следует использовать перечисление (Visual Basic)
Перечисления предоставляют простой способ работы с наборами связанных констант. Перечисление или `Enum`, является символическое имя для набора значений. Перечисления обрабатываются как типы данных и их можно использовать для создания наборов констант для использования с переменными и свойства.  
  
## <a name="when-to-use-an-enumeration"></a>Когда следует использовать перечисление  
 Когда процедура принимает ограниченный набор переменных, следует использовать перечисление. Перечисление делает код более удобочитаемым, особенно в том случае, если используются значимые имена.  
  
 Преимущества использования перечисления:  
  
-   Уменьшает количество ошибок, вызванных перемещением или неправильным вводом значений.  
  
-   Позволяет легко изменять значения в будущем.  
  
-   Делает код более удобным для чтения, это означает, что это снижает вероятность возникновения ошибок в нем.  
  
-   Обеспечение прямой совместимости. Для перечислений код является менее вероятны, если в будущем уведомлений об изменении значения, соответствующие именам элементов.  
  
## <a name="naming-enumerations"></a>Именование перечислений  
 Используйте соглашение об именовании для элементов перечисления. Когда [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] встречается имя члена перечисления, может быть исключение, если то же имя содержится в других библиотеках типов. Используйте уникальный префикс для идентификации значения из приложения или компонента.  
  
 При ссылке на член перечисления, вам необходимо уточнить имя члена с именем перечисления или воспользуйтесь `Imports` инструкции. Дополнительные сведения см. в разделе [перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## <a name="predefined-enumerations"></a>Предопределенные перечисления  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]предоставляет ряд стандартных перечислений, таких как `FirstDayOfWeek` и `MsgBoxResult`, для упрощения кода. Список этих разделе [константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## <a name="see-also"></a>См. также  
 [Как: объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Практическое руководство. Ссылка на элемент перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Как: перебор элементов перечисления в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [Практическое руководство. Определение строки, связанной со значением из перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [Оператор Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
