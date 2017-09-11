---
title: "&lt;para&gt; (руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <para>
- para
dev_langs:
- CSharp
helpviewer_keywords:
- <para> C# XML tag
- para C# XML tag
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 47f7469681f06bc8ed24b9d2c8f2c0cd43008726
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="ltparagt-c-programming-guide"></a><span data-ttu-id="8afed-102">&lt;para&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="8afed-102">&lt;para&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="8afed-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8afed-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8afed-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="8afed-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="8afed-105">Текст абзаца.</span><span class="sxs-lookup"><span data-stu-id="8afed-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8afed-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="8afed-106">Remarks</span></span>  
 <span data-ttu-id="8afed-107">Тег \<para> используется внутри другого тега, например [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md), [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) или [\<returns>](../../../csharp/programming-guide/xmldoc/returns.md), и позволяет добавить к тексту структуру.</span><span class="sxs-lookup"><span data-stu-id="8afed-107">The \<para> tag is for use inside a tag, such as [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md), [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md), or [\<returns>](../../../csharp/programming-guide/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="8afed-108">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="8afed-108">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8afed-109">Пример</span><span class="sxs-lookup"><span data-stu-id="8afed-109">Example</span></span>  
 <span data-ttu-id="8afed-110">В разделе [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) можно найти пример использования тега \<para>.</span><span class="sxs-lookup"><span data-stu-id="8afed-110">See [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) for an example of using \<para>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8afed-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8afed-111">See Also</span></span>  
 <span data-ttu-id="8afed-112">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8afed-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="8afed-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="8afed-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

