---
title: Руководство по программированию на C#. Тег &lt;para&gt;
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C# XML tag
- para C# XML tag
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
ms.openlocfilehash: e37f1b47ae1f45b29697fee220d99e6698a8c96d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498337"
---
# <a name="ltparagt-c-programming-guide"></a><span data-ttu-id="293df-102">&lt;para&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="293df-102">&lt;para&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="293df-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="293df-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="293df-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="293df-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="293df-105">Текст абзаца.</span><span class="sxs-lookup"><span data-stu-id="293df-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="293df-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="293df-106">Remarks</span></span>  
 <span data-ttu-id="293df-107">Тег \<para> используется внутри другого тега, например [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md), [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) или [\<returns>](../../../csharp/programming-guide/xmldoc/returns.md), и позволяет добавить к тексту структуру.</span><span class="sxs-lookup"><span data-stu-id="293df-107">The \<para> tag is for use inside a tag, such as [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md), [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md), or [\<returns>](../../../csharp/programming-guide/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="293df-108">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="293df-108">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="293df-109">Пример</span><span class="sxs-lookup"><span data-stu-id="293df-109">Example</span></span>  
 <span data-ttu-id="293df-110">В разделе [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) можно найти пример использования тега \<para>.</span><span class="sxs-lookup"><span data-stu-id="293df-110">See [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) for an example of using \<para>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="293df-111">См. также</span><span class="sxs-lookup"><span data-stu-id="293df-111">See also</span></span>

- [<span data-ttu-id="293df-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="293df-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="293df-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="293df-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
