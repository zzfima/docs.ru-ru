---
title: '&lt;Пример&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 2de91d828fd9706b66f4c810486e54e2d3062de0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524521"
---
# <a name="ltexamplegt-visual-basic"></a>&lt;Пример&gt; (Visual Basic)
Задает пример для элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<example>description</example>  
```  
  
#### <a name="parameters"></a>Параметры  
 `description`  
 Описание примера кода.  
  
## <a name="remarks"></a>Примечания  
 `<example>` Тег позволяет указать пример демонстрирует использование метода или другого элемента библиотеки. Вместе с ним часто применяется тег [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<example>` тега для включения примера использования `ID` поля.  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/example_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
