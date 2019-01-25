---
title: Как выполнить Создание XML-документации в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: d67724aad6cd3e7af30531328d85e89937390dd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551375"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Как выполнить Создание XML-документации в Visual Basic
В этом примере показано, как добавить в код комментарии XML-документации.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>Для создания XML-документации для типа или члена  
  
1.  В **редактор кода**, поместите курсор на одну строку выше типа или члена, для которого требуется создать документацию.  
  
2.  Тип `'''` (три знака одинарных кавычек).  
  
     Схема XML для типа или члена добавляется в **редактор кода**.  
  
3.  Добавление описательной информации между соответствующими тегами.  
  
    > [!NOTE]
    >  Если вы добавите дополнительные строки внутри блока XML-документации, каждая строка должна начинаться с `'''`.  
  
4.  Добавьте дополнительный код, который использует тип или член с новые комментарии XML-документации.  
  
     IntelliSense отображает текст из \<summary > тег для типа или члена.  
  
5.  Скомпилируйте код, чтобы создать XML-файл, содержащий комментарии к документации. Дополнительные сведения см. в разделе [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="see-also"></a>См. также
- [Документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
