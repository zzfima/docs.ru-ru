---
title: Использование исключений стандартных типов
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
author: KrzysztofCwalina
ms.openlocfilehash: b947c7cce057c060b1ab5054d1227f5703ccbf89
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543910"
---
# <a name="using-standard-exception-types"></a><span data-ttu-id="9e513-102">Использование исключений стандартных типов</span><span class="sxs-lookup"><span data-stu-id="9e513-102">Using Standard Exception Types</span></span>
<span data-ttu-id="9e513-103">В этом разделе описываются стандартные исключения, предоставляемые платформой и особенностей их использования.</span><span class="sxs-lookup"><span data-stu-id="9e513-103">This section describes the standard exceptions provided by the Framework and the details of their usage.</span></span> <span data-ttu-id="9e513-104">Список отнюдь не является исчерпывающим.</span><span class="sxs-lookup"><span data-stu-id="9e513-104">The list is by no means exhaustive.</span></span> <span data-ttu-id="9e513-105">Обратитесь к документации .NET Framework для использования другие типы исключений платформы.</span><span class="sxs-lookup"><span data-stu-id="9e513-105">Please refer to the .NET Framework reference documentation for usage of other Framework exception types.</span></span>  
  
## <a name="exception-and-systemexception"></a><span data-ttu-id="9e513-106">Исключение и SystemException</span><span class="sxs-lookup"><span data-stu-id="9e513-106">Exception and SystemException</span></span>  
 <span data-ttu-id="9e513-107">**X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> или <xref:System.SystemException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9e513-107">**X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> or <xref:System.SystemException?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="9e513-108">**X DO NOT** перехватывать `System.Exception` или `System.SystemException` в код платформы, если не требуется заново создать.</span><span class="sxs-lookup"><span data-stu-id="9e513-108">**X DO NOT** catch `System.Exception` or `System.SystemException` in framework code, unless you intend to rethrow.</span></span>  
  
 <span data-ttu-id="9e513-109">**X AVOID** перехват `System.Exception` или `System.SystemException`, за исключением обработчики исключений верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="9e513-109">**X AVOID** catching `System.Exception` or `System.SystemException`, except in top-level exception handlers.</span></span>  
  
## <a name="applicationexception"></a><span data-ttu-id="9e513-110">ApplicationException</span><span class="sxs-lookup"><span data-stu-id="9e513-110">ApplicationException</span></span>  
 <span data-ttu-id="9e513-111">**X DO NOT** throw или являются производными от <xref:System.ApplicationException>.</span><span class="sxs-lookup"><span data-stu-id="9e513-111">**X DO NOT** throw or derive from <xref:System.ApplicationException>.</span></span>  
  
## <a name="invalidoperationexception"></a><span data-ttu-id="9e513-112">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="9e513-112">InvalidOperationException</span></span>  
 <span data-ttu-id="9e513-113">**✓ DO** исключение <xref:System.InvalidOperationException> , если объект находится в недопустимом состоянии.</span><span class="sxs-lookup"><span data-stu-id="9e513-113">**✓ DO** throw an <xref:System.InvalidOperationException> if the object is in an inappropriate state.</span></span>  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a><span data-ttu-id="9e513-114">ArgumentException, ArgumentNullException и ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="9e513-114">ArgumentException, ArgumentNullException, and ArgumentOutOfRangeException</span></span>  
 <span data-ttu-id="9e513-115">**✓ DO** throw <xref:System.ArgumentException> или один из его подтипов, если член переданы недопустимые аргументы.</span><span class="sxs-lookup"><span data-stu-id="9e513-115">**✓ DO** throw <xref:System.ArgumentException> or one of its subtypes if bad arguments are passed to a member.</span></span> <span data-ttu-id="9e513-116">Предпочитаете наиболее производный тип исключения, если это применимо.</span><span class="sxs-lookup"><span data-stu-id="9e513-116">Prefer the most derived exception type, if applicable.</span></span>  
  
 <span data-ttu-id="9e513-117">**✓ DO** задать `ParamName` свойство при генерации один подклассы `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="9e513-117">**✓ DO** set the `ParamName` property when throwing one of the subclasses of `ArgumentException`.</span></span>  
  
 <span data-ttu-id="9e513-118">Это свойство представляет имя параметра, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="9e513-118">This property represents the name of the parameter that caused the exception to be thrown.</span></span> <span data-ttu-id="9e513-119">Обратите внимание, что свойство можно задать с помощью одной из перегрузок конструктора.</span><span class="sxs-lookup"><span data-stu-id="9e513-119">Note that the property can be set using one of the constructor overloads.</span></span>  
  
 <span data-ttu-id="9e513-120">**✓ DO** использовать `value` для имени неявного параметра значения методов установки свойств.</span><span class="sxs-lookup"><span data-stu-id="9e513-120">**✓ DO** use `value` for the name of the implicit value parameter of property setters.</span></span>  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a><span data-ttu-id="9e513-121">Исключение NullReferenceException, IndexOutOfRangeException и AccessViolationException</span><span class="sxs-lookup"><span data-stu-id="9e513-121">NullReferenceException, IndexOutOfRangeException, and AccessViolationException</span></span>  
 <span data-ttu-id="9e513-122">**X DO NOT** разрешить произвольного API-интерфейсы для явным или неявным образом вызывать <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, или <xref:System.IndexOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="9e513-122">**X DO NOT** allow publicly callable APIs to explicitly or implicitly throw <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, or <xref:System.IndexOutOfRangeException>.</span></span> <span data-ttu-id="9e513-123">Эти исключения зарезервированы и исключение подсистемой выполнения, так и в большинстве случаев указывать на ошибку.</span><span class="sxs-lookup"><span data-stu-id="9e513-123">These exceptions are reserved and thrown by the execution engine and in most cases indicate a bug.</span></span>  
  
 <span data-ttu-id="9e513-124">Выполните проверку, чтобы избежать возникновения этих исключений аргументов.</span><span class="sxs-lookup"><span data-stu-id="9e513-124">Do argument checking to avoid throwing these exceptions.</span></span> <span data-ttu-id="9e513-125">Эти исключения предоставляет сведения о реализации метода, могут измениться с течением времени.</span><span class="sxs-lookup"><span data-stu-id="9e513-125">Throwing these exceptions exposes implementation details of your method that might change over time.</span></span>  
  
## <a name="stackoverflowexception"></a><span data-ttu-id="9e513-126">Исключение StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="9e513-126">StackOverflowException</span></span>  
 <span data-ttu-id="9e513-127">**X DO NOT** явно вызывать <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="9e513-127">**X DO NOT** explicitly throw <xref:System.StackOverflowException>.</span></span> <span data-ttu-id="9e513-128">Исключение должно явно вызываться только средой CLR.</span><span class="sxs-lookup"><span data-stu-id="9e513-128">The exception should be explicitly thrown only by the CLR.</span></span>  
  
 <span data-ttu-id="9e513-129">**X DO NOT** перехватывать `StackOverflowException`.</span><span class="sxs-lookup"><span data-stu-id="9e513-129">**X DO NOT** catch `StackOverflowException`.</span></span>  
  
 <span data-ttu-id="9e513-130">Это почти невозможно написать управляемый код, который остается согласованным при наличии переполнения стека произвольные.</span><span class="sxs-lookup"><span data-stu-id="9e513-130">It is almost impossible to write managed code that remains consistent in the presence of arbitrary stack overflows.</span></span> <span data-ttu-id="9e513-131">Неуправляемые компоненты CLR остаются согласованными, с помощью проверок для перемещения переполнения стека, чтобы четко определенных местах, а не путем выхода из переполнения стека произвольные.</span><span class="sxs-lookup"><span data-stu-id="9e513-131">The unmanaged parts of the CLR remain consistent by using probes to move stack overflows to well-defined places rather than by backing out from arbitrary stack overflows.</span></span>  
  
## <a name="outofmemoryexception"></a><span data-ttu-id="9e513-132">OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="9e513-132">OutOfMemoryException</span></span>  
 <span data-ttu-id="9e513-133">**X DO NOT** явно вызывать <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="9e513-133">**X DO NOT** explicitly throw <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="9e513-134">Это исключение не должны вызываться только средой CLR.</span><span class="sxs-lookup"><span data-stu-id="9e513-134">This exception is to be thrown only by the CLR infrastructure.</span></span>  
  
## <a name="comexception-sehexception-and-executionengineexception"></a><span data-ttu-id="9e513-135">ComException SEHException и ExecutionEngineException</span><span class="sxs-lookup"><span data-stu-id="9e513-135">ComException, SEHException, and ExecutionEngineException</span></span>  
 <span data-ttu-id="9e513-136">**X DO NOT** явно вызывать <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, и <xref:System.Runtime.InteropServices.SEHException>.</span><span class="sxs-lookup"><span data-stu-id="9e513-136">**X DO NOT** explicitly throw <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, and <xref:System.Runtime.InteropServices.SEHException>.</span></span> <span data-ttu-id="9e513-137">Эти исключения должны вызываться только средой CLR.</span><span class="sxs-lookup"><span data-stu-id="9e513-137">These exceptions are to be thrown only by the CLR infrastructure.</span></span>  
  
 <span data-ttu-id="9e513-138">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="9e513-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9e513-139">*Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="9e513-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e513-140">См. также</span><span class="sxs-lookup"><span data-stu-id="9e513-140">See also</span></span>

- [<span data-ttu-id="9e513-141">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="9e513-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="9e513-142">Правила разработки исключений</span><span class="sxs-lookup"><span data-stu-id="9e513-142">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
