---
title: Практическое руководство. Создание XML-документации в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 7fb56da8a28367a6dcd5e28f208b4519510d7d95
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
