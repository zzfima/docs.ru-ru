---
title: "&lt;para&gt; (руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C# XML tag
- para C# XML tag
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d33355cde9c499c66b98780c088882376d8d0411
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltparagt-c-programming-guide"></a><span data-ttu-id="21352-102">&lt;para&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="21352-102">&lt;para&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="21352-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21352-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="21352-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="21352-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="21352-105">Текст абзаца.</span><span class="sxs-lookup"><span data-stu-id="21352-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21352-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="21352-106">Remarks</span></span>  
 <span data-ttu-id="21352-107">Тег \<para> используется внутри другого тега, например [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md), [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) или [\<returns>](../../../csharp/programming-guide/xmldoc/returns.md), и позволяет добавить к тексту структуру.</span><span class="sxs-lookup"><span data-stu-id="21352-107">The \<para> tag is for use inside a tag, such as [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md), [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md), or [\<returns>](../../../csharp/programming-guide/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="21352-108">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="21352-108">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21352-109">Пример</span><span class="sxs-lookup"><span data-stu-id="21352-109">Example</span></span>  
 <span data-ttu-id="21352-110">В разделе [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) можно найти пример использования тега \<para>.</span><span class="sxs-lookup"><span data-stu-id="21352-110">See [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) for an example of using \<para>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21352-111">См. также</span><span class="sxs-lookup"><span data-stu-id="21352-111">See Also</span></span>  
 [<span data-ttu-id="21352-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="21352-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="21352-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="21352-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
