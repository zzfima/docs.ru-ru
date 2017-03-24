---
title: "Практическое руководство: Создание XML-документации в Visual Basic | Документы Microsoft"
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
- XML comments
- XML documentation, creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
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
ms.openlocfilehash: 363a20c0fce05566b61e764d05932a9dfb779f90
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Практическое руководство. Создание XML-документации в Visual Basic
В этом примере показано, как добавить в код комментарии XML-документации.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>Создание XML-документации для типа или члена  
  
1.  В **редактор кода**, поместите курсор на одну строку выше типа или члена, для которого требуется создать документацию.  
  
2.  Тип `'''` (три знака одинарных кавычек).  
  
     Схема XML для типа или члена добавляется в **редактор кода**.  
  
3.  Добавление описательной информации между соответствующими тегами.  
  
    > [!NOTE]
    >  Если добавить дополнительные строки внутри блока XML-документации, каждая строка должна начинаться с `'''`.  
  
4.  Добавьте дополнительный код, который использует тип или член с новые комментарии XML-документации.  
  
     IntelliSense отображает текст из \<Сводка настроек тег для типа или члена.  
  
5.  Скомпилируйте код для создания XML-файл, содержащий комментарии к документации. Дополнительные сведения см. в разделе [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="see-also"></a>См. также  
 [Документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)   
 [Теги XML-комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)   
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
