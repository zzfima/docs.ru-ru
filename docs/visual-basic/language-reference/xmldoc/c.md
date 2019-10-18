---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 4ea19ed5330dcbb8fcd84708d1546a81d909b04e
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523940"
---
# <a name="c-visual-basic"></a>> \<c (Visual Basic)
Указывает, что текст в описании является кодом.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---|---|  
|`text`|Текст, который нужно указать в качестве кода.|  
  
## <a name="remarks"></a>Заметки  
 Тег `<c>` позволяет указать, что текст в описании должен быть помечен как код. Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется тег `<c>` в разделе сводки, чтобы указать, что `Counter` является кодом.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
