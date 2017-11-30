---
title: "&lt;включить&gt; (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22eebaa8da8ef082e132cfdf8cb68498bfe16d73
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltincludegt-visual-basic"></a>&lt;включить&gt; (Visual Basic)
Ссылается на другой файл, описывающий типы и члены в исходном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a>Параметры  
 `filename`  
 Обязательный. Имя файла, содержащего документацию. Имя файла может быть дополнено с указанием пути. Заключите `filename` в двойные кавычки (» «).  
  
 `tagpath`  
 Обязательный. Путь тегов в `filename`, который ведет к тегу `name`. Заключите путь в двойные кавычки (» «).  
  
 `name`  
 Обязательный. Спецификатор имени тега, который предшествует комментарии. `Name`будет иметь `id`.  
  
 `id`  
 Обязательный. Идентификатор тега, который предшествует комментариям. Заключите идентификатор в одинарные кавычки ("").  
  
## <a name="remarks"></a>Примечания  
 Используйте `<include>` тег для ссылок на комментарии в другом файле, описывающем типы и элементы в исходном коде. Этот способ является альтернативой размещению комментариев документации непосредственно в файле исходного кода.  
  
 `<include>` Тег использует рекомендация W3C языка XML Path (XPath) версии 1.0. Дополнительные сведения о способах настройки вашей `<include>` используйте найти по адресу http://www.w3.org/TR/xpath.  
  
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
