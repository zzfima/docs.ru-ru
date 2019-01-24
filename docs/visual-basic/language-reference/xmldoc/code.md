---
title: '&lt;код&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: 8a4708a7b50b0e221c1ebe7f95d4f8ff80cd1ebe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566311"
---
# <a name="ltcodegt-visual-basic"></a>&lt;код&gt; (Visual Basic)
Указывает, что текст является несколько строк кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<code>content</code>  
```  
  
#### <a name="parameters"></a>Параметры  
 `content`  
 Текст, который необходимо пометить как код.  
  
## <a name="remarks"></a>Примечания  
 Используйте `<code>` тег, чтобы указать несколько строк как код. С помощью тега [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) можно указать, что текст в описании необходимо пометить как код.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется \<кода > тег пример кода для использования `ID` поля.  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/code_1.vb)]  
  
## <a name="see-also"></a>См. также
- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
