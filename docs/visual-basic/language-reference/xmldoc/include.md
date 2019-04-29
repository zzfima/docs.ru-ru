---
title: <include> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: d9c1c1a50f0e3530c842a6058e288b8d2be15f95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940911"
---
# <a name="include-visual-basic"></a>\<включить > (Visual Basic)
Ссылается на другой файл, который описывает типы и члены в исходном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a>Параметры  
 `filename`  
 Обязательный. Имя файла, содержащего документацию. Имя файла может быть дополнено с указанием пути. Заключите `filename` в двойные кавычки (» «).  
  
 `tagpath`  
 Обязательный. Путь тегов в `filename`, который ведет к тегу `name`. Заключите путь в двойные кавычки (» «).  
  
 `name`  
 Обязательный. Спецификатор имени в теге, который предшествует комментариям. `Name` будет иметь `id`.  
  
 `id`  
 Обязательный. Идентификатор тега, который предшествует комментариям. Идентификатор заключается в одинарные кавычки ("").  
  
## <a name="remarks"></a>Примечания  
 Используйте `<include>` тег для ссылки на комментарии в другом файле, описывающем типы и члены в исходном коде. Этот способ является альтернативой размещению комментариев документации непосредственно в файле исходного кода.  
  
 `<include>` Тег использует в соответствии с рекомендацией W3C XML Path Language (XPath) версии 1.0. Дополнительные сведения о способах настройки вашего `<include>` использовать, см. в разделе <https://www.w3.org/TR/xpath>.  
  
## <a name="example"></a>Пример  
 В этом примере используется `<include>` тег для импорта из файла с именем члена комментарии к документации `commentFile.xml`.  
  
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
