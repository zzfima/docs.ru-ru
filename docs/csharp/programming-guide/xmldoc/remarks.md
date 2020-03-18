---
title: <remarks> Руководство по программированию на C#.
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: e37dac9cb9fed1df6ca027f09f2c95dbbc8ea66d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793374"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="1a24b-102">Руководство по программированию на C#. \<remarks></span><span class="sxs-lookup"><span data-stu-id="1a24b-102">\<remarks> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="1a24b-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a24b-103">Syntax</span></span>

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a><span data-ttu-id="1a24b-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="1a24b-104">Parameters</span></span>

- `Description`

  <span data-ttu-id="1a24b-105">Описание элемента.</span><span class="sxs-lookup"><span data-stu-id="1a24b-105">A description of the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="1a24b-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="1a24b-106">Remarks</span></span>

<span data-ttu-id="1a24b-107">Тег \<remarks> позволяет добавить сведения о типе, дополняющие информацию, указанную с помощью тега [\<summary>](./summary.md).</span><span class="sxs-lookup"><span data-stu-id="1a24b-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="1a24b-108">Эти сведения отображаются в окне "Обозреватель объектов".</span><span class="sxs-lookup"><span data-stu-id="1a24b-108">This information is displayed in the Object Browser window.</span></span>

<span data-ttu-id="1a24b-109">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="1a24b-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="1a24b-110">Пример</span><span class="sxs-lookup"><span data-stu-id="1a24b-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a><span data-ttu-id="1a24b-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1a24b-111">See also</span></span>

- [<span data-ttu-id="1a24b-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1a24b-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1a24b-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="1a24b-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
