---
title: Руководство по программированию на C#. Тег &lt;see&gt;
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 63476ff77f1a8286730f29149bb5b6b87779f144
ms.sourcegitcommit: deb9225a55485a5a6e6c7914deb30ccfceb69d3f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2019
ms.locfileid: "54058416"
---
# <a name="ltseegt-c-programming-guide"></a><span data-ttu-id="4194f-102">&lt;see&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="4194f-102">&lt;see&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="4194f-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4194f-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4194f-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="4194f-104">Parameters</span></span>  
 <span data-ttu-id="4194f-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="4194f-105">cref = " `member`"</span></span>  
 <span data-ttu-id="4194f-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="4194f-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="4194f-107">Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="4194f-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="4194f-108">*member* необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="4194f-108">Place *member* within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4194f-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4194f-109">Remarks</span></span>  
 <span data-ttu-id="4194f-110">Тег \<see> позволяет задать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="4194f-110">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="4194f-111">С помощью тега [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) можно указать, что текст должен быть размещен в разделе "См. также".</span><span class="sxs-lookup"><span data-stu-id="4194f-111">Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="4194f-112">Используйте [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) для создания внутренних гиперссылок на страницы документации для элементов кода.</span><span class="sxs-lookup"><span data-stu-id="4194f-112">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="4194f-113">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="4194f-113">Compile with [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="4194f-114">В следующем примере показан тег \<see> в разделе сводки.</span><span class="sxs-lookup"><span data-stu-id="4194f-114">The following example shows a \<see> tag within a summary section.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4194f-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4194f-115">See Also</span></span>

- [<span data-ttu-id="4194f-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4194f-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="4194f-117">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="4194f-117">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
