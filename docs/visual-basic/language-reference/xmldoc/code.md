---
title: '&lt;код&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: e66aebe35dd8f6443fefe3b07842b37270159e6e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43475989"
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
 [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
