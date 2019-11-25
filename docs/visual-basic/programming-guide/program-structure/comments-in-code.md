---
title: Комментарии в коде
ms.date: 07/20/2015
helpviewer_keywords:
- Uncomment button
- REM statement [Visual Basic]
- comments [Visual Basic], in code
- comments [Visual Basic], Visual Basic code
- Comment button
- buttons [Visual Basic], Uncomment
- buttons [Visual Basic], Comment
- code comments [Visual Basic], Visual Basic
- Visual Basic code, comments
- comments
- code comments
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
ms.openlocfilehash: 189810393db42c54cb8a0f97b22b3d1514d9a7c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346173"
---
# <a name="comments-in-code-visual-basic"></a>Комментарии в коде (Visual Basic)
В примерах кодов часто встречается символ начала комментария (`'`). This symbol tells the Visual Basic compiler to ignore the text following it, or the *comment*. Комментарии — это краткие заметки, внесенные в код, чтобы сделать чтение кода более легким.  
  
 Хорошим стилем программирования считается начинать все процедуры с краткого комментария, описывающего функциональные характеристики процедуры (то, что она делает). Это необходимо для вашего собственного удобства и удобства того, кто читает этот код. Следует отличать детали реализации (как процедура работает) от комментариев, описывающих функциональные характеристики. Если в комментарий включены детали реализации, их следует обновлять при редактировании кода.  
  
 Комментарии могут располагаться в конце той же строки, где содержится оператор, или занимать отдельную строку. Оба способа представлены в следующем коде:  
  
 [!code-vb[VbVbcnConventions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#16)]  
  
 Если комментарий занимает более одной строки, каждая строка должна начинаться с символа начала комментария, как показано в следующем примере.  
  
 [!code-vb[VbVbcnConventions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#17)]  
  
## <a name="commenting-guidelines"></a>Правила комментирования  
 В следующей таблице приведены общие рекомендации по тому, какие типы комментариев могут предшествовать разделу кода. These are suggestions; Visual Basic does not enforce rules for adding comments. В комментарий по желанию автора кода может быть включена любая информация.  
  
|||  
|---|---|  
|Тип комментария|Описание комментария|  
|Цель|Описание действий, совершаемых процедурой (но не того, каким образом совершаются эти действия)|  
|Допущения|Список всех внешних переменных, элементов управления, открытых файлов, к которым осуществляется доступ из процедуры|  
|Произведенный эффект|Список внешних переменных, элементов управления или файлов, на которые влияет данная процедура (если это влияние не очевидно)|  
|Inputs|Описание назначения аргументов|  
|Returns|Описание значений, возвращаемых процедурой|  
  
 Также рекомендуется принять во внимание следующие моменты.  
  
- Объявление каждой важной переменной должно предшествовать комментарию, описывающему ее назначение.  
  
- Имена переменных, элементов управления и процедур должны быть функционально понятными, чтобы комментарии требовались только в случае особо сложных деталей реализации.  
  
- Комментарии не могут располагаться за последовательностью продолжения строки в той же строке.  
  
 You can add or remove comment symbols for a block of code by selecting one or more lines of code and choosing the **Comment** (![The Visual Basic Comment button in Visual Studio.](./media/comments-in-code/visual-basic-comment-button.gif)) and **Uncomment** (![The Visual Basic Uncomment button in Visual Studio.](./media/comments-in-code/visual-basic-uncomment-button.gif)) buttons on the **Edit** toolbar.  
  
> [!NOTE]
> Кроме того, можно добавить в код комментарии, поставив в начале текста ключевое слово `REM`. However, the `'` symbol and the **Comment**/**Uncomment** buttons are easier to use and require less space and memory.  
  
## <a name="see-also"></a>См. также

- [Basic Instincts - Documenting Your Code With XML Comments](https://docs.microsoft.com/archive/msdn-magazine/2009/may/documenting-your-code-with-xml-comments)
- [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
- [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Оператор REM](../../../visual-basic/language-reference/statements/rem-statement.md)
