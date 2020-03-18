---
title: <permission> Руководство по программированию на C#.
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 4f76d28d5531c1b9f01fa950589407934cc1244a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77093478"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="ae8e1-102">Руководство по программированию на C#. \<permission></span><span class="sxs-lookup"><span data-stu-id="ae8e1-102">\<permission> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="ae8e1-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae8e1-103">Syntax</span></span>

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a><span data-ttu-id="ae8e1-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="ae8e1-104">Parameters</span></span>

- <span data-ttu-id="ae8e1-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="ae8e1-105">cref = " `member`"</span></span>

  <span data-ttu-id="ae8e1-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="ae8e1-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="ae8e1-107">Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="ae8e1-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="ae8e1-108">*member* необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="ae8e1-108">*member* must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="ae8e1-109">Сведения о создании ссылки cref на универсальный тип см. в статье об [атрибуте cref](./cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="ae8e1-109">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

- `description`

  <span data-ttu-id="ae8e1-110">Описание уровня доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="ae8e1-110">A description of the access to the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="ae8e1-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="ae8e1-111">Remarks</span></span>

<span data-ttu-id="ae8e1-112">Тег \<permission> tag позволяет документировать уровень доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="ae8e1-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="ae8e1-113">Задать уровень доступа для члена можно с помощью класса <xref:System.Security.PermissionSet>.</span><span class="sxs-lookup"><span data-stu-id="ae8e1-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>

<span data-ttu-id="ae8e1-114">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="ae8e1-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="ae8e1-115">Пример</span><span class="sxs-lookup"><span data-stu-id="ae8e1-115">Example</span></span>

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a><span data-ttu-id="ae8e1-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ae8e1-116">See also</span></span>

- [<span data-ttu-id="ae8e1-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ae8e1-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="ae8e1-118">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="ae8e1-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
