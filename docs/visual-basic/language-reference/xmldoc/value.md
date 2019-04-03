---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 2938d485bf6c547c792431b93fc8959c9c36befa
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821418"
---
# <a name="value-visual-basic"></a>\<Значение > (Visual Basic)
Указывает описание свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a>Параметры  
 `property-description`  
 Описание свойства.  
  
## <a name="remarks"></a>Примечания  
 Используйте `<value>` тегов для описания свойства. Обратите внимание, что при добавлении свойства с помощью мастера кода в среде разработки Visual Studio добавит [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) тег для нового свойства. Затем следует вручную добавить `<value>` тегов для описания значения, которое представляется свойством.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<value>` тегов для описания какое значение `Counter` содержится в свойстве.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
