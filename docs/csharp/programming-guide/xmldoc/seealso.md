---
title: '&lt;seealso&gt;. Руководство по программированию на C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
ms.openlocfilehash: e75480db9aebdeb2199694168abf4f774773b9c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543556"
---
# <a name="ltseealsogt-c-programming-guide"></a><span data-ttu-id="bbe5d-102">&lt;seealso&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="bbe5d-102">&lt;seealso&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="bbe5d-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bbe5d-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbe5d-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="bbe5d-104">Parameters</span></span>  
 <span data-ttu-id="bbe5d-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="bbe5d-105">cref = " `member`"</span></span>  
 <span data-ttu-id="bbe5d-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="bbe5d-107">Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных. `member`</span><span class="sxs-lookup"><span data-stu-id="bbe5d-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="bbe5d-108">необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="bbe5d-108">must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="bbe5d-109">Дополнительные сведения о создании ссылки cref на универсальный тип см. в разделе [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="bbe5d-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbe5d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="bbe5d-110">Remarks</span></span>  
 <span data-ttu-id="bbe5d-111">Кроме того, с помощью тега \<seealso> можно указать текст, который должен отображаться в разделе "См. также".</span><span class="sxs-lookup"><span data-stu-id="bbe5d-111">The \<seealso> tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="bbe5d-112">Тег [\<see>](../../../csharp/programming-guide/xmldoc/see.md) позволяет задать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-112">Use [\<see>](../../../csharp/programming-guide/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="bbe5d-113">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="bbe5d-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbe5d-114">Пример</span><span class="sxs-lookup"><span data-stu-id="bbe5d-114">Example</span></span>  
 <span data-ttu-id="bbe5d-115">В разделе [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) можно найти пример использования тега \<seealso>.</span><span class="sxs-lookup"><span data-stu-id="bbe5d-115">See [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) for an example of using \<seealso>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe5d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bbe5d-116">See also</span></span>

- [<span data-ttu-id="bbe5d-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="bbe5d-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="bbe5d-118">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="bbe5d-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
