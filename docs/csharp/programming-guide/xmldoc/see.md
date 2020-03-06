---
title: Руководство по программированию на C#. <see>
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
ms.openlocfilehash: f4834f88c646b44269f8290c2ad08698c34e714a
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627676"
---
# <a name="see-c-programming-guide"></a><span data-ttu-id="4b016-102">Руководство по программированию на C#. \<see></span><span class="sxs-lookup"><span data-stu-id="4b016-102">\<see> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="4b016-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b016-103">Syntax</span></span>

```xml
<see cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="4b016-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="4b016-104">Parameters</span></span>

- <span data-ttu-id="4b016-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="4b016-105">cref = "`member`"</span></span>

  <span data-ttu-id="4b016-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="4b016-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="4b016-107">Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="4b016-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="4b016-108">*member* необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="4b016-108">Place *member* within double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="4b016-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4b016-109">Remarks</span></span>

<span data-ttu-id="4b016-110">Тег \<see> позволяет задать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="4b016-110">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="4b016-111">С помощью тега [\<seealso>](./seealso.md) можно указать, что текст должен быть размещен в разделе "См. также".</span><span class="sxs-lookup"><span data-stu-id="4b016-111">Use [\<seealso>](./seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="4b016-112">Используйте [cref Attribute](./cref-attribute.md) для создания внутренних гиперссылок на страницы документации для элементов кода.</span><span class="sxs-lookup"><span data-stu-id="4b016-112">Use the [cref Attribute](./cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>

<span data-ttu-id="4b016-113">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="4b016-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="4b016-114">В следующем примере показан тег \<see> в разделе сводки.</span><span class="sxs-lookup"><span data-stu-id="4b016-114">The following example shows a \<see> tag within a summary section.</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a><span data-ttu-id="4b016-115">См. также</span><span class="sxs-lookup"><span data-stu-id="4b016-115">See also</span></span>

- [<span data-ttu-id="4b016-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4b016-116">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="4b016-117">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="4b016-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
