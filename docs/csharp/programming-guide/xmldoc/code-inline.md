---
title: <c> — руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: 8471681f979fdd030490a5ecc306c4a4b9f624f9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276761"
---
# <a name="c-c-programming-guide"></a>\<c> (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a>Параметры  
 `text`  
 Текст, который нужно указать в качестве кода.  
  
## <a name="remarks"></a>Примечания  
 С помощью тега \<c> можно указать, что текст в описании необходимо пометить как код. Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../csharp/programming-guide/xmldoc/code.md).  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/code-inline_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
