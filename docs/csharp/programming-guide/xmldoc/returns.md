---
title: <returns> — Руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: 873f515830c072f31548bee84a8ca9eec83fde27
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274144"
---
# <a name="returns-c-programming-guide"></a>\<returns> (Руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a>Параметры  
 `description`  
 Описание возвращаемого значения.  
  
## <a name="remarks"></a>Примечания  
 Тег \<returns> следует использовать в комментариях к объявлению метода для описания возвращаемого значения.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDocComments#10](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/returns_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
