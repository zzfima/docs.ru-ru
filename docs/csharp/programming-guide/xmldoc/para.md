---
title: '&lt;para&gt; (руководство по программированию на C#)'
ms.date: 07/20/2015
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C# XML tag
- para C# XML tag
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
ms.openlocfilehash: e51df23db97aadddbc4c4e8c3cb38bda7ff7e3a4
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44277027"
---
# <a name="ltparagt-c-programming-guide"></a><span data-ttu-id="b86e2-102">&lt;para&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="b86e2-102">&lt;para&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="b86e2-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b86e2-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b86e2-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="b86e2-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="b86e2-105">Текст абзаца.</span><span class="sxs-lookup"><span data-stu-id="b86e2-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b86e2-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="b86e2-106">Remarks</span></span>  
 <span data-ttu-id="b86e2-107">Тег \<para> используется внутри другого тега, например [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md), [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) или [\<returns>](../../../csharp/programming-guide/xmldoc/returns.md), и позволяет добавить к тексту структуру.</span><span class="sxs-lookup"><span data-stu-id="b86e2-107">The \<para> tag is for use inside a tag, such as [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md), [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md), or [\<returns>](../../../csharp/programming-guide/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="b86e2-108">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="b86e2-108">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b86e2-109">Пример</span><span class="sxs-lookup"><span data-stu-id="b86e2-109">Example</span></span>  
 <span data-ttu-id="b86e2-110">В разделе [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) можно найти пример использования тега \<para>.</span><span class="sxs-lookup"><span data-stu-id="b86e2-110">See [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) for an example of using \<para>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b86e2-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b86e2-111">See Also</span></span>

- [<span data-ttu-id="b86e2-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b86e2-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b86e2-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="b86e2-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
