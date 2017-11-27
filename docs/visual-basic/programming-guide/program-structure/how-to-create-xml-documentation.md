---
title: "Практическое руководство. Создание XML-документации в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 63b6485de5aba2ca49d54a057045bec2062d12dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Практическое руководство. Создание XML-документации в Visual Basic
В этом примере показано, как добавить в код комментарии XML-документации.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>Для создания XML-документации для типа или члена  
  
1.  В **редактор кода**, поместите курсор на строку выше тип или член, для которого требуется создать документацию.  
  
2.  Тип `'''` (три знака одинарных кавычек).  
  
     Схема XML для типа или члена добавляется в **редактор кода**.  
  
3.  Добавьте описательные сведения между соответствующими тегами.  
  
    > [!NOTE]
    >  Если добавить дополнительные строки внутри блока XML-документации, каждая строка должна начинаться с `'''`.  
  
4.  Добавьте дополнительный код, который использует тип или член с новые комментарии XML-документации.  
  
     IntelliSense отображает текст из \<сводки > тег для типа или члена.  
  
5.  Скомпилируйте код для создания XML-файл, содержащий комментарии документации. Дополнительные сведения см. в разделе [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="see-also"></a>См. также  
 [Документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
