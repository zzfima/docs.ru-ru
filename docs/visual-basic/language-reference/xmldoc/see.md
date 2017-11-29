---
title: "&lt;в разделе&gt; (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 010a3403d7748653648b323ad07f52bf93db2879
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltseegt-visual-basic"></a>&lt;в разделе&gt; (Visual Basic)
Указывает ссылку на другой член.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>Параметры  
 `member`  
 Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции. Компилятор проверяет, что данный элемент кода существует и передает `member` имени элемента в выходных данных XML. `member` необходимо заключать в двойные кавычки (" ").  
  
## <a name="remarks"></a>Примечания  
 Используйте `<see>` тег, чтобы указать ссылку в тексте. Используйте [ \<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) для указания текста, который может отображаться в разделе «См. также».  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<see>` тегом `UpdateRecord` раздел для обращения к примечаний `DoesRecordExist` метод.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/see_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
