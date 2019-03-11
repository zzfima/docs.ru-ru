---
title: <list> — Руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 9ac1d749d18a9d02ce28f8cf600495f345ec0e89
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489275"
---
# <a name="list-c-programming-guide"></a>\<list> (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<list type="bullet" | "number" | "table">  
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
 `term`  
 Термин, который будет определен в `description`.  
  
 `description`  
 Либо элемент маркированного или нумерованного списка, либо определение `term`.  
  
## <a name="remarks"></a>Примечания  
 Блок \<listheader> используется для определения строки заголовка в таблице или списке определений. При определении таблицы необходимо ввести данные для термина в заголовке.  
  
 Каждый элемент в списке указывается в блоке \<item>. При создании списка определений необходимо указать одновременно `term` и `description`. Тем не менее для таблицы, маркированного или нумерованного списка достаточно ввести только `description`.  
  
 Число блоков \<item> в списке или таблице не ограничено.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDocComments#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#6)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
