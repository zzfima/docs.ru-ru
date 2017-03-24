---
title: "Когда следует использовать перечисление (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f22102a2e1e7eafd7fcf4db1f46af2cc622eba70
ms.lasthandoff: 03/13/2017

---
# <a name="when-to-use-an-enumeration-visual-basic"></a>Когда следует использовать перечисление (Visual Basic)
Перечисления предоставляют простой способ работы с наборами связанных констант. Перечисление или `Enum`, является символическим именем для набора значений. Перечисления обрабатываются как типы данных и их можно использовать для создания наборов констант для использования с переменными и свойствами.  
  
## <a name="when-to-use-an-enumeration"></a>Когда следует использовать перечисление  
 Когда процедура принимает ограниченный набор переменных, следует использовать перечисление. Перечисление делает код более удобочитаемым, особенно при использовании осмысленных имен.  
  
 Преимущества использования перечисления:  
  
-   Уменьшает количество ошибок, вызванных перемещением или неправильным вводом значений.  
  
-   Позволяет легко изменять значения в будущем.  
  
-   Делает код более удобными для чтения, это означает, что это снижает вероятность возникновения ошибок в нем.  
  
-   Обеспечение прямой совместимости. Для перечислений код вероятность возникновения ошибок, если в будущем кто-то изменяет значения, соответствующие именам элементов.  
  
## <a name="naming-enumerations"></a>Именование перечислений  
 Используйте соглашения об именах для членов перечисления. Когда [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] встречается имя члена перечисления, может быть исключение, если то же имя содержится в других библиотеках типов. Используйте уникальный префикс для идентификации значения из приложения или компонента.  
  
 При ссылке на член перечисления, вам необходимо уточнить имя члена с помощью имени перечисления или воспользуйтесь `Imports` инструкции. Дополнительные сведения см. в разделе [перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## <a name="predefined-enumerations"></a>Предопределенные перечисления  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет ряд стандартных перечислений, таких как `FirstDayOfWeek` и `MsgBoxResul`t для упрощения кода. Список кодов см. [константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство: объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Практическое руководство: ссылка на член перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Практическое руководство: перебор элементов перечисления в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [Практическое руководство: определение строки, связанной со значением перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Оператор Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
