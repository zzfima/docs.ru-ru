---
title: "&lt;список&gt; (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 34347df88f1bc3097db0020526ec99943c8f7bd4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltlistgt-visual-basic"></a>&lt;список&gt; (Visual Basic)
Определяет список или таблицу.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<list type="type">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
#### <a name="parameters"></a>Параметры  
 `type`  
 Тип списка. Должно быть «bullet» для маркированного списка, «number» для нумерованного списка или «table» для двух столбцов таблицы.  
  
 `term`  
 Используется, только если `type` является «table». Термин, который определен в теге описания.  
  
 `description`  
 Когда `type` «bullet» или «number», `description` — это элемент в списке при `type` является «table» `description` является определением `term`.  
  
## <a name="remarks"></a>Примечания  
 `<listheader>` Блок определяет заголовок таблицы или определение списка. При определении таблицы достаточно указать запись для `term` в заголовке.  
  
 Каждый элемент в списке указывается в `<item>` блока. При создании списка определений, должны быть указаны `term` и `description`. Однако для таблицы, маркированного или нумерованного списка достаточно указать запись для `description`.  
  
 Список или таблица может иметь любое количество `<item>` блокируется при необходимости.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<list>` тег, чтобы определить маркированный список в разделе "Примечания".  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
