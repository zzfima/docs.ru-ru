---
title: '&lt;список&gt; (Visual Basic)'
ms.date: 07/20/2015
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
ms.openlocfilehash: 8d9bcffc32a1d1670aba1ce0e7b0ff0a6dc7112d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521118"
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
 Тип списка. Должно быть «bullet» для маркированного списка, «number» для нумерованного списка, или «table» для двух столбцов таблицы.  
  
 `term`  
 Используется, только если `type` является «table». Термин, который определен в теге description.  
  
 `description`  
 Когда `type` «bullet» или «number», `description` — это элемент в списке при `type` является «table», `description` является определением `term`.  
  
## <a name="remarks"></a>Примечания  
 `<listheader>` Блок определяет заголовок таблицы или определение списка. При определении таблицы необходимо только указать `term` в заголовке.  
  
 Каждый элемент в списке указывается с помощью `<item>` блока. При создании списка определений, должны быть указаны `term` и `description`. Тем не менее, для таблицы, маркированного или нумерованного списка достаточно указать `description`.  
  
 Список или таблица может быть столько `<item>` блокирует при необходимости.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<list>` тег для создания маркированного списка в разделе "Примечания".  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## <a name="see-also"></a>См. также
- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
