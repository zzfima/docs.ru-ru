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
ms.openlocfilehash: 807b2297dd1b8e00aa9b646f28fefbcb1148fe83
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237952"
---
# <a name="ltparagt-c-programming-guide"></a><span data-ttu-id="f087e-102">&lt;para&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f087e-102">&lt;para&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f087e-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f087e-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f087e-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="f087e-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="f087e-105">Текст абзаца.</span><span class="sxs-lookup"><span data-stu-id="f087e-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f087e-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="f087e-106">Remarks</span></span>  
 <span data-ttu-id="f087e-107">Тег \<para> используется внутри другого тега, например [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md), [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) или [\<returns>](../../../csharp/programming-guide/xmldoc/returns.md), и позволяет добавить к тексту структуру.</span><span class="sxs-lookup"><span data-stu-id="f087e-107">The \<para> tag is for use inside a tag, such as [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md), [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md), or [\<returns>](../../../csharp/programming-guide/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="f087e-108">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f087e-108">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f087e-109">Пример</span><span class="sxs-lookup"><span data-stu-id="f087e-109">Example</span></span>  
 <span data-ttu-id="f087e-110">В разделе [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) можно найти пример использования тега \<para>.</span><span class="sxs-lookup"><span data-stu-id="f087e-110">See [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) for an example of using \<para>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f087e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f087e-111">See Also</span></span>

- [<span data-ttu-id="f087e-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f087e-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f087e-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="f087e-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
