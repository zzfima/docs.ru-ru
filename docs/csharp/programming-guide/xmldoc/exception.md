---
title: Руководство по программированию на C#. <exception>
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 14318ac0b0cdf781d0488eecaf934879017d91f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789801"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="baeb7-102">Руководство по программированию на C#. \<exception></span><span class="sxs-lookup"><span data-stu-id="baeb7-102">\<exception> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="baeb7-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="baeb7-103">Syntax</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="parameters"></a><span data-ttu-id="baeb7-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="baeb7-104">Parameters</span></span>

- <span data-ttu-id="baeb7-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="baeb7-105">cref = " `member`"</span></span>

  <span data-ttu-id="baeb7-106">Ссылка на исключение, которое доступно из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="baeb7-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="baeb7-107">Компилятор проверяет, существует ли исключение, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="baeb7-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="baeb7-108">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="baeb7-108">`member` must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="baeb7-109">См. подробнее о том, как форматировать `member`, чтобы создать ссылку на универсальный тип, в руководстве по [обработке XML-файла](processing-the-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="baeb7-109">For more information on how to format `member` to reference a generic type, see [Processing the XML File](processing-the-xml-file.md).</span></span>

- `description`

  <span data-ttu-id="baeb7-110">Описание исключения.</span><span class="sxs-lookup"><span data-stu-id="baeb7-110">A description of the exception.</span></span>

## <a name="remarks"></a><span data-ttu-id="baeb7-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="baeb7-111">Remarks</span></span>

<span data-ttu-id="baeb7-112">Тег \<exception> служит для указания возможных исключений.</span><span class="sxs-lookup"><span data-stu-id="baeb7-112">The \<exception> tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="baeb7-113">Этот тег может применяться к определениям методов, свойств, событий и индексаторов.</span><span class="sxs-lookup"><span data-stu-id="baeb7-113">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>

<span data-ttu-id="baeb7-114">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="baeb7-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="baeb7-115">Дополнительные сведения об обработке исключений см. в разделе [Исключения и обработка исключений](../exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="baeb7-115">For more information about exception handling, see [Exceptions and Exception Handling](../exceptions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="baeb7-116">Пример</span><span class="sxs-lookup"><span data-stu-id="baeb7-116">Example</span></span>

[!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]

## <a name="see-also"></a><span data-ttu-id="baeb7-117">См. также</span><span class="sxs-lookup"><span data-stu-id="baeb7-117">See also</span></span>

- [<span data-ttu-id="baeb7-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="baeb7-118">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="baeb7-119">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="baeb7-119">Recommended tags for documentation comments</span></span>](recommended-tags-for-documentation-comments.md)
