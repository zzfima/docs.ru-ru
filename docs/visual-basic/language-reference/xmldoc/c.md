---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 2fa6e66771ac854421d07a5f33e116f12516dad6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260208"
---
# <a name="c-visual-basic"></a>\<c > (Visual Basic)
Указывает, что текст в описании кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---|---|  
|`text`|Текст, который нужно указать в качестве кода.|  
  
## <a name="remarks"></a>Примечания  
 `<c>` Тег дает возможность указать, что текст в описании должен быть помечен как код. Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<c>` тег в разделе сводки, чтобы указать, что `Counter` — это код.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a>См. также
- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
