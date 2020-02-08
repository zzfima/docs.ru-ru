---
title: <seealso> Руководство по программированию на C#.
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
ms.openlocfilehash: ad22b423d085a152f47c4e34d7ee4247ef9836b8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789684"
---
# <a name="seealso-c-programming-guide"></a><span data-ttu-id="9778c-102">Руководство по программированию на C#. \<seealso></span><span class="sxs-lookup"><span data-stu-id="9778c-102">\<seealso> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="9778c-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9778c-103">Syntax</span></span>

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="9778c-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="9778c-104">Parameters</span></span>

- <span data-ttu-id="9778c-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="9778c-105">cref = " `member`"</span></span>

  <span data-ttu-id="9778c-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="9778c-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="9778c-107">Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных. `member`</span><span class="sxs-lookup"><span data-stu-id="9778c-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="9778c-108">необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="9778c-108">must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="9778c-109">Дополнительные сведения о создании ссылки cref на универсальный тип см. в разделе [\<see>](./see.md).</span><span class="sxs-lookup"><span data-stu-id="9778c-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="9778c-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="9778c-110">Remarks</span></span>

<span data-ttu-id="9778c-111">Кроме того, с помощью тега \<seealso> можно указать текст, который должен отображаться в разделе "См. также".</span><span class="sxs-lookup"><span data-stu-id="9778c-111">The \<seealso> tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="9778c-112">Тег [\<see>](./see.md) позволяет задать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="9778c-112">Use [\<see>](./see.md) to specify a link from within text.</span></span>

<span data-ttu-id="9778c-113">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="9778c-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="9778c-114">Пример</span><span class="sxs-lookup"><span data-stu-id="9778c-114">Example</span></span>

<span data-ttu-id="9778c-115">В разделе [\<summary>](./summary.md) можно найти пример использования тега \<seealso>.</span><span class="sxs-lookup"><span data-stu-id="9778c-115">See [\<summary>](./summary.md) for an example of using \<seealso>.</span></span>

## <a name="see-also"></a><span data-ttu-id="9778c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9778c-116">See also</span></span>

- [<span data-ttu-id="9778c-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9778c-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="9778c-118">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="9778c-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
