---
title: <see> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: c26e818276eb4654fec77230372a0ae090952961
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474856"
---
# <a name="see-visual-basic"></a>\<см. в разделе > (Visual Basic)
Указывает ссылку на другой член.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a>Параметры  
 `member`  
 Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции. Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных. `member` необходимо заключать в двойные кавычки (" ").  
  
## <a name="remarks"></a>Примечания  
 Используйте `<see>` тег, чтобы указать ссылку из текста. Используйте [ \<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) для указания текста, который может отображаться в разделе «См. также».  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<see>` тегом `UpdateRecord` раздел для ссылки на примечаний `DoesRecordExist` метод.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также
- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
