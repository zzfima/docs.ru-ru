---
title: '&lt;paramref&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 153f5ddeeb7d09159049af4d466b0695f5cb6f23
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393449"
---
# <a name="ltparamrefgt-visual-basic"></a>&lt;paramref&gt; (Visual Basic)
Форматирует слово в качестве параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a>Параметры  
 `name`  
 Имя параметра, на который указывается ссылка. Имя заключается в двойные кавычки (" ").  
  
## <a name="remarks"></a>Примечания  
 `<paramref>` Тег дает возможность указать, что слово является параметром. Чтобы этот параметр особым образом могут обрабатываться XML-файле.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<paramref>` тег для ссылки на `id` параметра.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/paramref_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
