---
title: <inheritdoc> — руководство по программированию на C#
ms.date: 01/21/2020
f1_keywords:
- inheritdoc
- <inheritdoc>
helpviewer_keywords:
- <inheritdoc> C# XML tag
- inheritdoc C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 6f42462f21d045428577cd2123e2180d866f1e1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156952"
---
# <a name="inheritdoc-c-programming-guide"></a><span data-ttu-id="ec948-102">\<inheritdoc> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="ec948-102">\<inheritdoc> (C# Programming Guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="ec948-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec948-103">Syntax</span></span>  
  
```xml  
<inheritdoc/>
```  

## <a name="inheritdoc"></a><span data-ttu-id="ec948-104">InheritDoc</span><span class="sxs-lookup"><span data-stu-id="ec948-104">InheritDoc</span></span>

<span data-ttu-id="ec948-105">Наследование XML-комментариев от базовых классов, интерфейсов и аналогичных методов.</span><span class="sxs-lookup"><span data-stu-id="ec948-105">Inherit XML comments from base classes, interfaces, and similar methods.</span></span> <span data-ttu-id="ec948-106">Это позволяет обойтись без копирования и вставки одинаковых XML-комментариев и автоматически поддерживать их синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="ec948-106">This eliminates unwanted copying and pasting of duplicate XML comments and automatically keeps XML comments synchronized.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ec948-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="ec948-107">Remarks</span></span>  
<span data-ttu-id="ec948-108">Добавьте XML-комментарии в базовые классы или интерфейсы, и InheritDoc скопирует их во все реализации классов.</span><span class="sxs-lookup"><span data-stu-id="ec948-108">Add your XML comments in base classes or interfaces and let InheritDoc copy the comments to implementing classes.</span></span>

<span data-ttu-id="ec948-109">Добавьте XML-комментарии в синхронные методы, и InheritDoc скопирует их в асинхронные версии аналогичных методов.</span><span class="sxs-lookup"><span data-stu-id="ec948-109">Add your XML comments to your synchronous methods and let InheritDoc copy the comments to your asynchronous versions of the same methods.</span></span>  

<span data-ttu-id="ec948-110">Если вам нужно скопировать комментарии из определенного элемента, укажите нужный элемент в атрибуте `cref`.</span><span class="sxs-lookup"><span data-stu-id="ec948-110">If you want to copy the comments from a specific member you can use the `cref` attribute to specify the member.</span></span>
  
## <a name="examples"></a><span data-ttu-id="ec948-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="ec948-111">Examples</span></span>
[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a><span data-ttu-id="ec948-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ec948-112">See also</span></span>

- [<span data-ttu-id="ec948-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ec948-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ec948-114">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="ec948-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
