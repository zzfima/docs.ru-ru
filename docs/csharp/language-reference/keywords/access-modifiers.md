---
title: Справочник по C#. Модификаторы доступа
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: 754949e42771de30cc2dce7e4e610f70ada6dfd4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713847"
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="cd356-102">Модификаторы доступа (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="cd356-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="cd356-103">Модификаторы доступа — это ключевые слова, которые задают объявленный уровень доступности члена или типа.</span><span class="sxs-lookup"><span data-stu-id="cd356-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="cd356-104">В этом разделе описываются четыре модификатора доступа:</span><span class="sxs-lookup"><span data-stu-id="cd356-104">This section introduces the four access modifiers:</span></span>  
  
- `public`
- `protected`
- `internal`
- `private`
  
 <span data-ttu-id="cd356-105">С помощью этих модификаторов можно задать следующие шесть уровней доступа:</span><span class="sxs-lookup"><span data-stu-id="cd356-105">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="cd356-106">[`public`](public.md): Неограниченный доступ.</span><span class="sxs-lookup"><span data-stu-id="cd356-106">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="cd356-107">[`protected`](protected.md): Доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="cd356-107">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="cd356-108">[`internal`](internal.md): Доступ ограничен текущей сборкой.</span><span class="sxs-lookup"><span data-stu-id="cd356-108">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="cd356-109">[`protected internal`](protected-internal.md): Доступ ограничен текущей сборкой или типами, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="cd356-109">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="cd356-110">[`private`](private.md): Доступ ограничен содержащим типом.</span><span class="sxs-lookup"><span data-stu-id="cd356-110">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="cd356-111">[`private protected`](private-protected.md): Доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса в текущей сборке.</span><span class="sxs-lookup"><span data-stu-id="cd356-111">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="cd356-112">В этом разделе также представлена следующая информация:</span><span class="sxs-lookup"><span data-stu-id="cd356-112">This section also introduces the following:</span></span>  
  
- <span data-ttu-id="cd356-113">[Уровни доступности](./accessibility-levels.md). С помощью четырех модификаторов доступа можно объявить шесть уровней доступности.</span><span class="sxs-lookup"><span data-stu-id="cd356-113">[Accessibility Levels](./accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
- <span data-ttu-id="cd356-114">[Домен доступности](./accessibility-domain.md). Определяет, в каких разделах программы может присутствовать ссылка на этот элемент.</span><span class="sxs-lookup"><span data-stu-id="cd356-114">[Accessibility Domain](./accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
- <span data-ttu-id="cd356-115">[Ограничения на использование уровней доступности](./restrictions-on-using-accessibility-levels.md). Общие сведения об ограничениях на использование объявленных уровней доступности.</span><span class="sxs-lookup"><span data-stu-id="cd356-115">[Restrictions on Using Accessibility Levels](./restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd356-116">См. также</span><span class="sxs-lookup"><span data-stu-id="cd356-116">See also</span></span>

- [<span data-ttu-id="cd356-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="cd356-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cd356-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="cd356-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cd356-119">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="cd356-119">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="cd356-120">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="cd356-120">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="cd356-121">Ключевые слова доступа</span><span class="sxs-lookup"><span data-stu-id="cd356-121">Access Keywords</span></span>](base.md)
- [<span data-ttu-id="cd356-122">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="cd356-122">Modifiers</span></span>](index.md)
