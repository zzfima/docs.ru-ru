---
title: "&lt;see&gt; (руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <see>
- see
dev_langs:
- CSharp
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
caps.latest.revision: 19
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
ms.openlocfilehash: 831caae9574c25f16e8b2ede734746f48019198e
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="ltseegt-c-programming-guide"></a><span data-ttu-id="aaffe-102">&lt;see&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="aaffe-102">&lt;see&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="aaffe-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aaffe-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aaffe-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="aaffe-104">Parameters</span></span>  
 <span data-ttu-id="aaffe-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="aaffe-105">cref = " `member`"</span></span>  
 <span data-ttu-id="aaffe-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="aaffe-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="aaffe-107">Компилятор проверяет существование указанного элемента кода и передает имя элемента `member` в выходных данных XML. Имя *члена* заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="aaffe-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.Place *member* within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aaffe-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="aaffe-108">Remarks</span></span>  
 <span data-ttu-id="aaffe-109">Тег \<see> позволяет задать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="aaffe-109">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="aaffe-110">С помощью тега [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) можно указать, что текст должен быть размещен в разделе "См. также".</span><span class="sxs-lookup"><span data-stu-id="aaffe-110">Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="aaffe-111">Используйте [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) для создания внутренних гиперссылок на страницы документации для элементов кода.</span><span class="sxs-lookup"><span data-stu-id="aaffe-111">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="aaffe-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="aaffe-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="aaffe-113">В следующем примере показан тег \<see> в разделе сводки.</span><span class="sxs-lookup"><span data-stu-id="aaffe-113">The following example shows a \<see> tag within a summary section.</span></span>  
  
 <span data-ttu-id="aaffe-114">[!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="aaffe-114">[!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaffe-115">См. также</span><span class="sxs-lookup"><span data-stu-id="aaffe-115">See Also</span></span>  
 <span data-ttu-id="aaffe-116">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="aaffe-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="aaffe-117">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="aaffe-117">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

