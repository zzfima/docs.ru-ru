---
title: "Модификаторы (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- keywords [C#], modifiers
- modifiers [C#]
ms.assetid: c96691dd-b357-49ec-b5ae-03ca214fadfb
caps.latest.revision: 18
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
ms.openlocfilehash: 9e2e7e5e3907ac9bb66676e749ddd55a8ac4836c
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="modifiers-c-reference"></a><span data-ttu-id="f66fd-102">Модификаторы (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f66fd-102">Modifiers (C# Reference)</span></span>
<span data-ttu-id="f66fd-103">Модификаторы служат для изменения объявлений типов и их членов.</span><span class="sxs-lookup"><span data-stu-id="f66fd-103">Modifiers are used to modify declarations of types and type members.</span></span> <span data-ttu-id="f66fd-104">В этом разделе описаны модификаторы C#.</span><span class="sxs-lookup"><span data-stu-id="f66fd-104">This section introduces the C# modifiers.</span></span>  
  
|<span data-ttu-id="f66fd-105">Модификатор</span><span class="sxs-lookup"><span data-stu-id="f66fd-105">Modifier</span></span>|<span data-ttu-id="f66fd-106">Цель</span><span class="sxs-lookup"><span data-stu-id="f66fd-106">Purpose</span></span>|  
|--------------|-------------|  
|[<span data-ttu-id="f66fd-107">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="f66fd-107">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)<br /><br /> <span data-ttu-id="f66fd-108">-   [public](../../../csharp/language-reference/keywords/public.md)</span><span class="sxs-lookup"><span data-stu-id="f66fd-108">-   [public](../../../csharp/language-reference/keywords/public.md)</span></span><br /><span data-ttu-id="f66fd-109">-   [private](../../../csharp/language-reference/keywords/private.md)</span><span class="sxs-lookup"><span data-stu-id="f66fd-109">-   [private](../../../csharp/language-reference/keywords/private.md)</span></span><br /><span data-ttu-id="f66fd-110">-   [internal](../../../csharp/language-reference/keywords/internal.md)</span><span class="sxs-lookup"><span data-stu-id="f66fd-110">-   [internal](../../../csharp/language-reference/keywords/internal.md)</span></span><br /><span data-ttu-id="f66fd-111">-   [protected](../../../csharp/language-reference/keywords/protected.md)</span><span class="sxs-lookup"><span data-stu-id="f66fd-111">-   [protected](../../../csharp/language-reference/keywords/protected.md)</span></span>|<span data-ttu-id="f66fd-112">Задает уровень доступа к типам и их членам.</span><span class="sxs-lookup"><span data-stu-id="f66fd-112">Specifies the declared accessibility of types and type members.</span></span>|  
|[<span data-ttu-id="f66fd-113">abstract</span><span class="sxs-lookup"><span data-stu-id="f66fd-113">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="f66fd-114">Указывает на то, что класс предназначен только для использования в качестве базового класса других классов.</span><span class="sxs-lookup"><span data-stu-id="f66fd-114">Indicates that a class is intended only to be a base class of other classes.</span></span>|  
|[<span data-ttu-id="f66fd-115">async</span><span class="sxs-lookup"><span data-stu-id="f66fd-115">async</span></span>](../../../csharp/language-reference/keywords/async.md)|<span data-ttu-id="f66fd-116">Указывает на то, что измененный метод, лямбда-выражение или анонимный метод является асинхронным.</span><span class="sxs-lookup"><span data-stu-id="f66fd-116">Indicates that the modified method, lambda expression, or anonymous method is asynchronous.</span></span>|  
|[<span data-ttu-id="f66fd-117">const</span><span class="sxs-lookup"><span data-stu-id="f66fd-117">const</span></span>](../../../csharp/language-reference/keywords/const.md)|<span data-ttu-id="f66fd-118">Указывает на то, что значение поля или локальной переменной не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="f66fd-118">Specifies that the value of the field or the local variable cannot be modified.</span></span>|  
|[<span data-ttu-id="f66fd-119">event</span><span class="sxs-lookup"><span data-stu-id="f66fd-119">event</span></span>](../../../csharp/language-reference/keywords/event.md)|<span data-ttu-id="f66fd-120">Объявление события.</span><span class="sxs-lookup"><span data-stu-id="f66fd-120">Declares an event.</span></span>|  
|[<span data-ttu-id="f66fd-121">extern</span><span class="sxs-lookup"><span data-stu-id="f66fd-121">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)|<span data-ttu-id="f66fd-122">Указывает на то, что метод имеет внешнюю реализацию.</span><span class="sxs-lookup"><span data-stu-id="f66fd-122">Indicates that the method is implemented externally.</span></span>|  
|[<span data-ttu-id="f66fd-123">new</span><span class="sxs-lookup"><span data-stu-id="f66fd-123">new</span></span>](../../../csharp/language-reference/keywords/new.md)|<span data-ttu-id="f66fd-124">Явно скрывает член, унаследованный от базового класса.</span><span class="sxs-lookup"><span data-stu-id="f66fd-124">Explicitly hides a member inherited from a base class.</span></span>|  
|[<span data-ttu-id="f66fd-125">override</span><span class="sxs-lookup"><span data-stu-id="f66fd-125">override</span></span>](../../../csharp/language-reference/keywords/override.md)|<span data-ttu-id="f66fd-126">Обеспечивает новую реализацию виртуального члена, унаследованного от базового класса.</span><span class="sxs-lookup"><span data-stu-id="f66fd-126">Provides a new implementation of a virtual member inherited from a base class.</span></span>|  
|[<span data-ttu-id="f66fd-127">partial</span><span class="sxs-lookup"><span data-stu-id="f66fd-127">partial</span></span>](../../../csharp/language-reference/keywords/partial-type.md)|<span data-ttu-id="f66fd-128">Определяет разделяемые классы, структуры и методы в рамках одной сборки.</span><span class="sxs-lookup"><span data-stu-id="f66fd-128">Defines partial classes, structs and methods throughout the same assembly.</span></span>|  
|[<span data-ttu-id="f66fd-129">readonly</span><span class="sxs-lookup"><span data-stu-id="f66fd-129">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)|<span data-ttu-id="f66fd-130">Объявляет поле, которому можно присваивать значения только в рамках объявления или в конструкторе этого же класса.</span><span class="sxs-lookup"><span data-stu-id="f66fd-130">Declares a field that can only be assigned values as part of the declaration or in a constructor in the same class.</span></span>|  
|[<span data-ttu-id="f66fd-131">sealed</span><span class="sxs-lookup"><span data-stu-id="f66fd-131">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)|<span data-ttu-id="f66fd-132">Указывает на то, что класс не может наследоваться.</span><span class="sxs-lookup"><span data-stu-id="f66fd-132">Specifies that a class cannot be inherited.</span></span>|  
|[<span data-ttu-id="f66fd-133">static</span><span class="sxs-lookup"><span data-stu-id="f66fd-133">static</span></span>](../../../csharp/language-reference/keywords/static.md)|<span data-ttu-id="f66fd-134">Объявляет член, который относится к типу, а не к конкретному объекту.</span><span class="sxs-lookup"><span data-stu-id="f66fd-134">Declares a member that belongs to the type itself instead of to a specific object.</span></span>|  
|[<span data-ttu-id="f66fd-135">unsafe</span><span class="sxs-lookup"><span data-stu-id="f66fd-135">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)|<span data-ttu-id="f66fd-136">Объявляет небезопасный контекст.</span><span class="sxs-lookup"><span data-stu-id="f66fd-136">Declares an unsafe context.</span></span>|  
|[<span data-ttu-id="f66fd-137">virtual</span><span class="sxs-lookup"><span data-stu-id="f66fd-137">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="f66fd-138">Объявляет обычный метод или метод доступа, реализацию которых можно изменить путем переопределения члена в производном классе.</span><span class="sxs-lookup"><span data-stu-id="f66fd-138">Declares a method or an accessor whose implementation can be changed by an overriding member in a derived class.</span></span>|  
|[<span data-ttu-id="f66fd-139">volatile</span><span class="sxs-lookup"><span data-stu-id="f66fd-139">volatile</span></span>](../../../csharp/language-reference/keywords/volatile.md)|<span data-ttu-id="f66fd-140">Указывает на то, что поле может быть изменено в программе операционной системой, оборудованием, параллельным потоком и т. д.</span><span class="sxs-lookup"><span data-stu-id="f66fd-140">Indicates that a field can be modified in the program by something such as the operating system, the hardware, or a concurrently executing thread.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f66fd-141">См. также</span><span class="sxs-lookup"><span data-stu-id="f66fd-141">See Also</span></span>  
 <span data-ttu-id="f66fd-142">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f66fd-142">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f66fd-143">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f66fd-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="f66fd-144">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f66fd-144">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

