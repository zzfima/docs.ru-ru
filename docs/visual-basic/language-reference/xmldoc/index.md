---
title: Рекомендуемые XML-теги для комментариев документации
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 093c967557b899c8661fdec348d421996e948b94
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352337"
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
|[исключение\<>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<включить >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para>](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<разрешение >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<см. >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<value>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 (<sup>1</sup> компилятор проверяет синтаксис.)  
  
> [!NOTE]
> Если необходимо, чтобы угловые скобки отображались в тексте комментария к документации, используйте `&lt;` и `&gt;`. Например, строка `"&lt;text in angle brackets&gt;"` будет выглядеть как `<text in angle brackets>`.  
  
## <a name="see-also"></a>См. также

- [Документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)
- [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
