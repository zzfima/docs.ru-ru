---
title: "Комментарии в коде (Visual Basic) | Документы Microsoft"
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
- Uncomment button
- REM statement
- comments, in code
- comments, Visual Basic code
- Comment button
- buttons, Uncomment
- buttons, Comment
- code comments, Visual Basic
- Visual Basic code, comments
- comments
- code comments
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
caps.latest.revision: 17
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
ms.openlocfilehash: 9663d83903ba2f9dcf93ecb5c293ac479e7dc175
ms.lasthandoff: 03/13/2017

---
# <a name="comments-in-code-visual-basic"></a>Комментарии в коде (Visual Basic)
В примерах кодов часто встречается символ начала комментария (`'`). Этот символ дает [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятору инструкцию проигнорировать последующий текст, или *комментарий*. Комментарии — это краткие заметки, внесенные в код, чтобы сделать чтение кода более легким.  
  
 Хорошим стилем программирования считается начинать все процедуры с краткого комментария, описывающего функциональные характеристики процедуры (то, что она делает). Это необходимо для вашего собственного удобства и удобства того, кто читает этот код. Следует отличать детали реализации (как процедура работает) от комментариев, описывающих функциональные характеристики. Если в комментарий включены детали реализации, их следует обновлять при редактировании кода.  
  
 Комментарии могут располагаться в конце той же строки, где содержится оператор, или занимать отдельную строку. Оба способа представлены в следующем коде:  
  
 [!code-vb[VbVbcnConventions №&16;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_1.vb)]  
  
 Если комментарий занимает более одной строки, каждая строка должна начинаться с символа начала комментария, как показано в следующем примере.  
  
 [!code-vb[VbVbcnConventions&17;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_2.vb)]  
  
## <a name="commenting-guidelines"></a>Правила комментирования  
 В следующей таблице приведены общие рекомендации по тому, какие типы комментариев могут предшествовать разделу кода. Данная информация носит рекомендательный характер; в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] нет жестких норм, касающихся добавления комментариев. В комментарий по желанию автора кода может быть включена любая информация.  
  
|||  
|---|---|  
|Тип комментария|Описание комментария|  
|Назначение|Описание действий, совершаемых процедурой (но не того, каким образом совершаются эти действия)|  
|Допущения|Список всех внешних переменных, элементов управления, открытых файлов, к которым осуществляется доступ из процедуры |  
|Произведенный эффект|Список внешних переменных, элементов управления или файлов, на которые влияет данная процедура (если это влияние не очевидно)|  
|Inputs|Описание назначения аргументов|  
|Returns|Описание значений, возвращаемых процедурой|  
  
 Также рекомендуется принять во внимание следующие моменты.  
  
-   Объявление каждой важной переменной должно предшествовать комментарию, описывающему ее назначение.  
  
-   Имена переменных, элементов управления и процедур должны быть функционально понятными, чтобы комментарии требовались только в случае особо сложных деталей реализации.  
  
-   Комментарии не могут располагаться за последовательностью продолжения строки в той же строке.  
  
 Можно добавить или удалить символы комментария для блок кода, выбрав одну или несколько строк кода и выбрав **комментарий** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "vaCommentButton")) и **Uncomment** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "vaUncommentButton")) кнопки на **изменить** инструментов.  
  
> [!NOTE]
>  Кроме того, можно добавить в код комментарии, поставив в начале текста ключевое слово `REM`. Тем не менее `'` символов и **комментарий**/**Uncomment** кнопки легче использовать и требует меньше места и памяти.  
  
## <a name="see-also"></a>См. также  
 [Документирование кода с комментариями XML](http://msdn.microsoft.com/magazine/dd722812.aspx)   
 [Практическое руководство: Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)   
 [Теги XML-комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)   
 [Структура программы и соглашения о коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Оператор REM](../../../visual-basic/language-reference/statements/rem-statement.md)
