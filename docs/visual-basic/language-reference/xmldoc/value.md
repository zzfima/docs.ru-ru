---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 516ff6ba534478d066b8ca06baee46bdd4b35265
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524602"
---
# <a name="value-visual-basic"></a>> \<value (Visual Basic)
Задает описание свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a>Параметры  
 `property-description`  
 Описание свойства.  
  
## <a name="remarks"></a>Заметки  
 Для описания свойства используйте тег `<value>`. Обратите внимание, что при добавлении свойства с помощью мастера кода в среде разработки Visual Studio будет добавлен тег [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) для нового свойства. Затем следует вручную добавить тег `<value>` для описания значения, которое представляет свойство.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется тег `<value>` для описания значения, которое содержит свойство `Counter`.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
