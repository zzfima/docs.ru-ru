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
ms.openlocfilehash: d660cb1739733c4e98ae0b7939476fe74e6cf200
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794837"
---
# <a name="inheritdoc-c-programming-guide"></a><span data-ttu-id="3c48e-102">\<inheritdoc> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="3c48e-102">\<inheritdoc> (C# Programming Guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="3c48e-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c48e-103">Syntax</span></span>  
  
```xml  
<inheritdoc/> 
```  

## <a name="inheritdoc"></a><span data-ttu-id="3c48e-104">InheritDoc</span><span class="sxs-lookup"><span data-stu-id="3c48e-104">InheritDoc</span></span>

<span data-ttu-id="3c48e-105">Наследование XML-комментариев от базовых классов, интерфейсов и аналогичных методов.</span><span class="sxs-lookup"><span data-stu-id="3c48e-105">Inherit XML comments from base classes, interfaces, and similar methods.</span></span> <span data-ttu-id="3c48e-106">Это позволяет обойтись без копирования и вставки одинаковых XML-комментариев и автоматически поддерживать их синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="3c48e-106">This eliminates unwanted copying and pasting of duplicate XML comments and automatically keeps XML comments synchronized.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="3c48e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="3c48e-107">Remarks</span></span>  
<span data-ttu-id="3c48e-108">Добавьте XML-комментарии в базовые классы или интерфейсы, и InheritDoc скопирует их во все реализации классов.</span><span class="sxs-lookup"><span data-stu-id="3c48e-108">Add your XML comments in base classes or interfaces and let InheritDoc copy the comments to implementing classes.</span></span>

<span data-ttu-id="3c48e-109">Добавьте XML-комментарии в синхронные методы, и InheritDoc скопирует их в асинхронные версии аналогичных методов.</span><span class="sxs-lookup"><span data-stu-id="3c48e-109">Add your XML comments to your synchronous methods and let InheritDoc copy the comments to your asynchronous versions of the same methods.</span></span>  

<span data-ttu-id="3c48e-110">Если вам нужно скопировать комментарии из определенного элемента, укажите нужный элемент в атрибуте `cref`.</span><span class="sxs-lookup"><span data-stu-id="3c48e-110">If you want to copy the comments from a specific member you can use the `cref` attribute to specify the member.</span></span>
  
## <a name="examples"></a><span data-ttu-id="3c48e-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="3c48e-111">Examples</span></span>
[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a><span data-ttu-id="3c48e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3c48e-112">See also</span></span>

- [<span data-ttu-id="3c48e-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3c48e-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3c48e-114">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="3c48e-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
