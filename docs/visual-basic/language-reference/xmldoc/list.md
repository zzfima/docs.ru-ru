---
title: <list> (Visual Basic)
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
ms.openlocfilehash: 5d4295d485611e75e8b6c8d8f95e079654f0cfa3
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524747"
---
# <a name="list-visual-basic"></a>> \<list (Visual Basic)
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
  
## <a name="parameters"></a>Параметры  
 `type`  
 Тип списка. Должен быть "маркированным" для маркированного списка, "число" для нумерованного списка или "Таблица" для таблицы из двух столбцов.  
  
 `term`  
 Используется, только если `type` имеет значение "Table". Термин для определения, который определен в теге description.  
  
 `description`  
 Если `type` имеет значение "маркированный" или "число", `description` является элементом списка, если `type` "Таблица", `description` является определением `term`.  
  
## <a name="remarks"></a>Заметки  
 Блок `<listheader>` определяет заголовок таблицы или списка определений. При определении таблицы необходимо указать в заголовке только запись для `term`.  
  
 Каждый элемент в списке задается блоком `<item>`. При создании списка определений необходимо указать и `term`, и `description`. Однако для таблицы, маркированного списка или нумерованного списка необходимо указать только запись для `description`.  
  
 Список или таблица может содержать столько `<item>` блоков, сколько необходимо.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере тег `<list>` используется для определения маркированного списка в разделе "Примечания".  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
