---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: b220c2a9aa544413c3692485f6c1eb2b64e54389
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524684"
---
# <a name="returns-visual-basic"></a>> \<returns (Visual Basic)
Задает возвращаемое значение свойства или функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a>Параметры  
 `description`  
 Описание возвращаемого значения.  
  
## <a name="remarks"></a>Заметки  
 Используйте тег `<returns>` в комментарии для объявления метода, чтобы описать возвращаемое значение.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется тег `<returns>` для объяснения того, что возвращает функция `DoesRecordExist`.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
