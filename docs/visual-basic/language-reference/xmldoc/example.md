---
title: "&lt;Пример&gt; (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e34b75f4ce924a35dd5396b449730316025a9f35
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
 `<example>` Тег позволяет указывать пример того, как использовать метод или другой элемент библиотеки. Вместе с ним часто применяется тег [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<example>` тег, чтобы включить пример с использованием `ID` поля.  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/example_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
