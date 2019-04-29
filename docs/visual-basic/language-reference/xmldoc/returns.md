---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 5a0ff0da7cf26a1cea75a5b2e4678593d9b72f54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940794"
---
# <a name="returns-visual-basic"></a>\<Возвращает > (Visual Basic)
Указывает возвращаемое значение свойства или функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a>Параметры  
 `description`  
 Описание возвращаемого значения.  
  
## <a name="remarks"></a>Примечания  
 Используйте `<returns>` тег в комментариях к объявлению метода для описания возвращаемого значения.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<returns>` тег, чтобы объяснить, что `DoesRecordExist` возврата функции.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
