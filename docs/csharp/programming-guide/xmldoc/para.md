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
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44181358"
---
# <a name="ltparagt-c-programming-guide"></a><span data-ttu-id="15684-102">&lt;para&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="15684-102">&lt;para&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="15684-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15684-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15684-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="15684-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="15684-105">Текст абзаца.</span><span class="sxs-lookup"><span data-stu-id="15684-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15684-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="15684-106">Remarks</span></span>  
 <span data-ttu-id="15684-107">Тег \<para> используется внутри другого тега, например [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md), [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) или [\<returns>](../../../csharp/programming-guide/xmldoc/returns.md), и позволяет добавить к тексту структуру.</span><span class="sxs-lookup"><span data-stu-id="15684-107">The \<para> tag is for use inside a tag, such as [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md), [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md), or [\<returns>](../../../csharp/programming-guide/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="15684-108">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="15684-108">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15684-109">Пример</span><span class="sxs-lookup"><span data-stu-id="15684-109">Example</span></span>  
 <span data-ttu-id="15684-110">В разделе [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) можно найти пример использования тега \<para>.</span><span class="sxs-lookup"><span data-stu-id="15684-110">See [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) for an example of using \<para>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15684-111">См. также</span><span class="sxs-lookup"><span data-stu-id="15684-111">See Also</span></span>

- [<span data-ttu-id="15684-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="15684-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="15684-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="15684-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
