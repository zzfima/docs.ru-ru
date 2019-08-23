---
title: Рекомендуется использовать XML-теги для комментариев документации (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 2d6519af8ca1a0e2d59131eec4d63646dce7318b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913501"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>Рекомендуется использовать XML-теги для комментариев документации (Visual Basic)
Компилятор Visual Basic может обрабатывать комментарии документации в коде в XML-файле. Для обработки XML-файла в документации можно использовать дополнительные средства.  
  
 Комментарии XML разрешены в конструкциях кода, таких как типы и члены типов. Для разделяемых типов только одна часть типа может содержать комментарии XML, хотя не существует ограничений на комментирование его элементов.  
  
> [!NOTE]
> Комментарии к документации нельзя применять к пространствам имен. Причина состоит в том, что одно пространство имен может охватывать несколько сборок, и не все сборки должны быть загружены одновременно.  
  
 Компилятор обрабатывает любой тег, который является допустимым XML. Следующие теги предоставляют часто используемые функции в пользовательской документации.  
  
||||  
|---|---|---|  
|[\<c>](../../../visual-basic/language-reference/xmldoc/c.md)|[\<code>](../../../visual-basic/language-reference/xmldoc/code.md)|[\<example>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|исключение > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/exception.md)|включить > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/include.md)|[\<list>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para>](../../../visual-basic/language-reference/xmldoc/para.md)|параметр > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/param.md)|[\<paramref>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|разрешение > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/permission.md)|[\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|см. > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/see.md)|seeAlso > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/seealso.md)|[\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|typeparam > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/typeparam.md)|[\<value>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 (<sup>1</sup> компилятор проверяет синтаксис.)  
  
> [!NOTE]
> Если необходимо, чтобы угловые скобки отображались в тексте комментария к документации `&lt;` , `&gt;`используйте и. Например, строка `"&lt;text in angle brackets&gt;"` будет выглядеть так `<text in angle brackets>`:.  
  
## <a name="see-also"></a>См. также

- [Документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
- [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
