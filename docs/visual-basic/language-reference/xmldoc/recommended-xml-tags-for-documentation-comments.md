---
title: "Рекомендуемые XML-теги для комментариев документации (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlDocComment
dev_langs:
- VB
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 14
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
ms.openlocfilehash: c6a47c12bc24864ef6ac9f80054becad98ec97f1
ms.lasthandoff: 03/13/2017

---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>Рекомендуется использовать XML-теги для комментариев документации (Visual Basic)
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор может обрабатывать комментарии в коде в XML-файл. Можно использовать дополнительные средства для обработки XML-файла в документации.  
  
 Комментарии XML разрешены в конструкциях кода, таких как типы и члены типов. Для разделяемых типов только одна часть типа может содержать комментарии XML, несмотря на то, что нет ограничений на комментирование его членов.  
  
> [!NOTE]
>  Комментарии документации не может применяться к пространствам имен. Это связано с одним пространством имен может охватывать несколько сборок, что не все сборки должны загружаться в то же время.  
  
 Компилятор обрабатывает любой тег, допустимый XML-код. Следующие теги предоставляют часто используемые возможности в пользовательской документации.  
  
||||  
|---|---|---|  
|[\<c настроек](../../../visual-basic/language-reference/xmldoc/c.md)|[\<Код настроек](../../../visual-basic/language-reference/xmldoc/code.md)|[\<Пример настроек](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<исключение настроек](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<включить настроек](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para настроек](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref настроек](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<разрешение настроек](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<Примечания настроек](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<Возвращает настроек](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|[\<seealso настроек](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<Сводка настроек](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|[\<typeparam настроек](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<значения настроек](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 (<sup>1</sup> компилятор проверяет синтаксис.)  
  
> [!NOTE]
>  Угловые скобки в текст комментария документации, используйте `<` и `>`. Например, строка `"<text in angle brackets>"` будет отображаться как `<text in angle``brackets>`.  
  
## <a name="see-also"></a>См. также  
 [Документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)   
 [/ doc](../../../visual-basic/reference/command-line-compiler/doc.md)   
 [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
