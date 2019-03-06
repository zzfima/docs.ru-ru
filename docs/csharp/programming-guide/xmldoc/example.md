---
title: <example> — Руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C# XML tag
- example C# XML tag
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
ms.openlocfilehash: e7a829596d167e470790294f19e2d5b5aa86cfcf
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972824"
---
# <a name="example-c-programming-guide"></a>\<example> (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<example>description</example>  
```  
  
#### <a name="parameters"></a>Параметры  
 `description`  
 Описание примера кода.  
  
## <a name="remarks"></a>Примечания  
 Тег \<example> позволяет указать пример использования метода или другого элемента библиотеки. Вместе с ним часто применяется тег [\<code>](../../../csharp/programming-guide/xmldoc/code.md).  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
