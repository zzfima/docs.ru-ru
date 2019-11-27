---
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 2f2bebfd06d4614f05cb66834cc5bef40524ce3b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348459"
---
# <a name="include-visual-basic"></a>\<включить > (Visual Basic)
Ссылается на другой файл, описывающий типы и члены в исходном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a>Параметры  
 `filename`  
 Обязательно. Имя файла, содержащего документацию. Имя файла может быть дополнено с указанием пути. Заключите `filename` в двойные кавычки ("").  
  
 `tagpath`  
 Обязательно. Путь тегов в `filename`, который ведет к тегу `name`. Заключите путь в двойные кавычки ("").  
  
 `name`  
 Обязательно. Описатель имени в теге, который предшествует комментариям. `Name` будет иметь `id`.  
  
 `id`  
 Обязательно. Идентификатор тега, который предшествует комментариям. Заключите идентификатор в одинарные кавычки (' ').  
  
## <a name="remarks"></a>Примечания  
 Используйте тег `<include>` для ссылки на комментарии в другом файле, описывающем типы и члены в исходном коде. Этот способ является альтернативой размещению комментариев документации непосредственно в файле исходного кода.  
  
 Тег `<include>` использует рекомендацию консорциума W3C по языку XML-пути (XPath) версии 1,0. Дополнительные сведения о способах настройки `<include>` использования см. в разделе <https://www.w3.org/TR/xpath>.  
  
## <a name="example"></a>Пример  
 В этом примере тег `<include>` используется для импорта комментариев документации элемента из файла с именем `commentFile.xml`.  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
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

- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
