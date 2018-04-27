---
title: Перегрузка членов
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 546db0540cf7852b40678476f732663369b15824
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="member-overloading"></a><span data-ttu-id="e974e-102">Перегрузка членов</span><span class="sxs-lookup"><span data-stu-id="e974e-102">Member Overloading</span></span>
<span data-ttu-id="e974e-103">Перегрузка членов означает создание двух или более элементов в рамках одного типа, отличающихся только число или тип параметров, но имеют одинаковое имя.</span><span class="sxs-lookup"><span data-stu-id="e974e-103">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="e974e-104">Например, в следующих `WriteLine` перегруженный метод:</span><span class="sxs-lookup"><span data-stu-id="e974e-104">For example, in the following, the `WriteLine` method is overloaded:</span></span>  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 <span data-ttu-id="e974e-105">Так как только методы, конструкторы и индексированных свойств могут содержать параметры, только тех элементов, могут быть перегружены.</span><span class="sxs-lookup"><span data-stu-id="e974e-105">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>  
  
 <span data-ttu-id="e974e-106">Перегрузка является одним из наиболее важных способы улучшения удобства использования, производительность и удобство чтения повторно используемых библиотек.</span><span class="sxs-lookup"><span data-stu-id="e974e-106">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="e974e-107">Перегрузка на число параметров позволяет предоставлять более простой версии конструкторы и методы.</span><span class="sxs-lookup"><span data-stu-id="e974e-107">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="e974e-108">Перегрузка в параметре-типе дает возможность использовать одно и то же имя члена для идентичных операций с выбранным набором различных типов элементов.</span><span class="sxs-lookup"><span data-stu-id="e974e-108">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>  
  
 <span data-ttu-id="e974e-109">**✓ СДЕЛАТЬ** попробуйте использовать описательные имена параметров, чтобы указать значение по умолчанию использовать более короткие перегрузки.</span><span class="sxs-lookup"><span data-stu-id="e974e-109">**✓ DO** try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>  
  
 <span data-ttu-id="e974e-110">**X ИЗБЕГАЙТЕ** произвольного изменения имен параметров в перегрузках.</span><span class="sxs-lookup"><span data-stu-id="e974e-110">**X AVOID** arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="e974e-111">Если параметр в одной перегрузке представляет одного входного параметра в другую перегрузку, должен иметь то же имя.</span><span class="sxs-lookup"><span data-stu-id="e974e-111">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>  
  
 <span data-ttu-id="e974e-112">**X ИЗБЕГАЙТЕ** Несогласованная в порядок параметров в перегруженных членов.</span><span class="sxs-lookup"><span data-stu-id="e974e-112">**X AVOID** being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="e974e-113">Параметры с тем же именем, должны отображаться в той же позиции в все перегрузки.</span><span class="sxs-lookup"><span data-stu-id="e974e-113">Parameters with the same name should appear in the same position in all overloads.</span></span>  
  
 <span data-ttu-id="e974e-114">**✓ СДЕЛАТЬ** сделать виртуальной только самую длинную перегрузку (если требуется расширяемость).</span><span class="sxs-lookup"><span data-stu-id="e974e-114">**✓ DO** make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="e974e-115">Более короткие перегрузки должны просто вызвать через более.</span><span class="sxs-lookup"><span data-stu-id="e974e-115">Shorter overloads should simply call through to a longer overload.</span></span>  
  
 <span data-ttu-id="e974e-116">**X не** использовать `ref` или `out` модификаторы для перегрузки членов.</span><span class="sxs-lookup"><span data-stu-id="e974e-116">**X DO NOT** use `ref` or `out` modifiers to overload members.</span></span>  
  
 <span data-ttu-id="e974e-117">В некоторых языках не может разрешить вызовы перегрузки следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e974e-117">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="e974e-118">Кроме того таких перегрузок обычно имеют совершенно разные семантики и, возможно, не должно быть перегрузки, но два отдельных метода вместо.</span><span class="sxs-lookup"><span data-stu-id="e974e-118">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>  
  
 <span data-ttu-id="e974e-119">**X не** имеют перегрузки с параметрами в одной позиции и похожих, но различную семантику.</span><span class="sxs-lookup"><span data-stu-id="e974e-119">**X DO NOT** have overloads with parameters at the same position and similar types yet with different semantics.</span></span>  
  
 <span data-ttu-id="e974e-120">**СДЕЛАТЬ ✓** Разрешить `null` для передачи дополнительных аргументов.</span><span class="sxs-lookup"><span data-stu-id="e974e-120">**✓ DO**  allow `null` to be passed for optional arguments.</span></span>  
  
 <span data-ttu-id="e974e-121">**✓ СДЕЛАТЬ** использовать член перегрузка предпочтительнее, чем определение членов с аргументами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e974e-121">**✓ DO** use member overloading rather than defining members with default arguments.</span></span>  
  
 <span data-ttu-id="e974e-122">Аргументы по умолчанию не являются CLS-совместимыми.</span><span class="sxs-lookup"><span data-stu-id="e974e-122">Default arguments are not CLS compliant.</span></span>  
  
 <span data-ttu-id="e974e-123">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="e974e-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e974e-124">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="e974e-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e974e-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e974e-125">See Also</span></span>  
 [<span data-ttu-id="e974e-126">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="e974e-126">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="e974e-127">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="e974e-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
