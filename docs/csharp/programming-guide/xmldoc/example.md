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
ms.openlocfilehash: 17956838c20a4342873478869c07c6382f037fcb
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523510"
---
# <a name="example-c-programming-guide"></a>\<example> (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a>Параметры  
 `description`  
 Описание примера кода.  
  
## <a name="remarks"></a>Примечания  
 Тег \<example> позволяет указать пример использования метода или другого элемента библиотеки. Вместе с ним часто применяется тег [\<code>](./code.md).  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
