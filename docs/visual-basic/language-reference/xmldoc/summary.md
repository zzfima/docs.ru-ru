---
title: '&lt;Сводка&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 5ef9b7a98503ff36174de4418ca7d599c365f5aa
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43671391"
---
# <a name="ltsummarygt-visual-basic"></a>&lt;Сводка&gt; (Visual Basic)
Задает сводку элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a>Параметры  
 `description`  
 Сводка объекта.  
  
## <a name="remarks"></a>Примечания  
 Используйте `<summary>` тегов для описания типа или члена типа. Чтобы добавить дополнительную информацию в описание типа, используйте [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md).  
  
 Текст для `<summary>` тег является единственным источником сведений о типе для технологии IntelliSense, а также отображается в обозревателе объектов. Сведения об обозревателе объектов см. в разделе [Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<summary>` тегов для описания `ResetCounter` метод и `Counter` свойство.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
