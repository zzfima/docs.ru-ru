---
title: '&lt;seealso&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a1acbf2ee8f416e28987cc9d63dd3bf6d8c2dcf3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltseealsogt-visual-basic"></a>&lt;seealso&gt; (Visual Basic)
Указывает ссылку, которая отображается в разделе см.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a>Параметры  
 `member`  
 Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции. Компилятор проверяет, что данный элемент кода существует и передает `member` имени элемента в выходных данных XML. `member` необходимо заключать в двойные кавычки (" ").  
  
## <a name="remarks"></a>Примечания  
 Используйте `<seealso>` тег, чтобы указать текст, который будет отображаться в разделе см. Тег [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) позволяет задать ссылку из текста.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<seealso>` тегом `DoesRecordExist` раздел для обращения к примечаний `UpdateRecord` метод.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
