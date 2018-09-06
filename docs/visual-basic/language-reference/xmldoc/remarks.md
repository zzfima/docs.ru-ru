---
title: '&lt;"Примечания"&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 97fca8758d9c21ac0b8f15bf9d5831750fbabe77
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43746971"
---
# <a name="ltremarksgt-visual-basic"></a>&lt;"Примечания"&gt; (Visual Basic)
Задает раздел "Примечания" для элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>Параметры  
 `description`  
 Описание элемента.  
  
## <a name="remarks"></a>Примечания  
 Используйте `<remarks>` тег для добавления сведений о типе, дополняющие информацию, указанный с помощью [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md).  
  
 Эта информация отображается в обозревателе объектов. Сведения об обозревателе объектов см. в разделе [Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<remarks>` тег, чтобы объяснить, что `UpdateRecord` делает метод.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
