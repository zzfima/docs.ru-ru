---
title: '&lt;see&gt; (руководство по программированию на C#)'
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
ms.openlocfilehash: c37ad869b3eb904377cd4470a85cd557f6560290
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "45749678"
---
# <a name="ltseegt-c-programming-guide"></a><span data-ttu-id="34911-102">&lt;see&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="34911-102">&lt;see&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="34911-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34911-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34911-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="34911-104">Parameters</span></span>  
 <span data-ttu-id="34911-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="34911-105">cref = " `member`"</span></span>  
 <span data-ttu-id="34911-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="34911-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="34911-107">Компилятор проверяет существование указанного элемента кода и передает имя элемента `member` в выходных данных XML. Имя *члена* заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="34911-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.Place *member* within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34911-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="34911-108">Remarks</span></span>  
 <span data-ttu-id="34911-109">Тег \<see> позволяет задать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="34911-109">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="34911-110">С помощью тега [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) можно указать, что текст должен быть размещен в разделе "См. также".</span><span class="sxs-lookup"><span data-stu-id="34911-110">Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="34911-111">Используйте [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) для создания внутренних гиперссылок на страницы документации для элементов кода.</span><span class="sxs-lookup"><span data-stu-id="34911-111">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="34911-112">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="34911-112">Compile with [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="34911-113">В следующем примере показан тег \<see> в разделе сводки.</span><span class="sxs-lookup"><span data-stu-id="34911-113">The following example shows a \<see> tag within a summary section.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="34911-114">См. также</span><span class="sxs-lookup"><span data-stu-id="34911-114">See Also</span></span>

- [<span data-ttu-id="34911-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="34911-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="34911-116">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="34911-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
