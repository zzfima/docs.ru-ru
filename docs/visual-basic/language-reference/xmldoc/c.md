---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: d8efd2359ecb65bec1b427d8b1dca4b0c88a1152
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469031"
---
# <a name="c-visual-basic"></a>\<c > (Visual Basic)
Указывает, что текст в описании кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
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
