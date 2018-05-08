---
title: '&lt;включить&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 65bc0439696612cd8331a9c0718efcfee83af574
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ltincludegt-visual-basic"></a>&lt;включить&gt; (Visual Basic)
Ссылается на другой файл, описывающий типы и члены в исходном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a>Параметры  
 `filename`  
 Обязательно. Имя файла, содержащего документацию. Имя файла может быть дополнено с указанием пути. Заключите `filename` в двойные кавычки (» «).  
  
 `tagpath`  
 Обязательно. Путь тегов в `filename`, который ведет к тегу `name`. Заключите путь в двойные кавычки (» «).  
  
 `name`  
 Обязательно. Спецификатор имени тега, который предшествует комментарии. `Name` будет иметь `id`.  
  
 `id`  
 Обязательно. Идентификатор тега, который предшествует комментариям. Заключите идентификатор в одинарные кавычки ("").  
  
## <a name="remarks"></a>Примечания  
 Используйте `<include>` тег для ссылок на комментарии в другом файле, описывающем типы и элементы в исходном коде. Этот способ является альтернативой размещению комментариев документации непосредственно в файле исходного кода.  
  
 `<include>` Тег использует рекомендация W3C языка XML Path (XPath) версии 1.0. Дополнительные сведения о способах настройки вашей `<include>` используйте доступен на http://www.w3.org/TR/xpath.  
  
## <a name="example"></a>Пример  
 В этом примере используется `<include>` тег, чтобы импортировать член комментарии из файла с именем `commentFile.xml`.  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 Формат `commentFile.xml` выглядит следующим образом.  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a>См. также  
 [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
