---
title: <typeparam> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: d7fb980545a532e39310ea3e9d663a2b5a81a006
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968456"
---
# <a name="typeparam-visual-basic"></a>\<typeparam > (Visual Basic)
Определяет имя параметра типа и описание.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a>Параметры  
 `name`  
 Имя параметра типа. Имя заключается в двойные кавычки (" ").  
  
 `description`  
 Описание параметра типа.  
  
## <a name="remarks"></a>Примечания  
 Используйте `<typeparam>` тег в комментарии для универсального типа или объявление универсального члена для описания одного из параметров типа.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<typeparam>` тегов для описания `id` параметра.  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a>См. также
- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
