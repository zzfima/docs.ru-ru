---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 9be9f9e96fc1b79ea97d54c54352da63b93ef264
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838044"
---
# <a name="c-visual-basic"></a>\<c > (Visual Basic)
Указывает, что текст в описании кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---|---|  
|`text`|Текст, который нужно указать в качестве кода.|  
  
## <a name="remarks"></a>Примечания  
 `<c>` Тег дает возможность указать, что текст в описании должен быть помечен как код. Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<c>` тег в разделе сводки, чтобы указать, что `Counter` — это код.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
