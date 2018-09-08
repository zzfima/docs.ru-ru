---
title: Перегрузка членов
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2127497d294cbfd4e1bb24d033f432378627ff13
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208235"
---
# <a name="member-overloading"></a><span data-ttu-id="68267-102">Перегрузка членов</span><span class="sxs-lookup"><span data-stu-id="68267-102">Member Overloading</span></span>
<span data-ttu-id="68267-103">Перегрузка членов означает создание двух или более элементов на том же типе, отличающиеся только количество и тип параметров, но иметь то же имя.</span><span class="sxs-lookup"><span data-stu-id="68267-103">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="68267-104">Например, в следующих `WriteLine` метод перегружен:</span><span class="sxs-lookup"><span data-stu-id="68267-104">For example, in the following, the `WriteLine` method is overloaded:</span></span>  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 <span data-ttu-id="68267-105">Так как только методы, конструкторы и индексированных свойств могут содержать параметры, только тех элементов могут быть перегружены.</span><span class="sxs-lookup"><span data-stu-id="68267-105">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>  
  
 <span data-ttu-id="68267-106">Перегрузка — один из наиболее важных способов повышения удобства использования, производительность и удобство чтения повторно используемых библиотек.</span><span class="sxs-lookup"><span data-stu-id="68267-106">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="68267-107">Перегрузка на число параметров позволяет предоставлять более простой версии конструкторы и методы.</span><span class="sxs-lookup"><span data-stu-id="68267-107">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="68267-108">Перегрузка к типу параметра дает возможность использовать одно и то же имя члена для членов, идентичные операций с выбранным набором различных типов.</span><span class="sxs-lookup"><span data-stu-id="68267-108">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>  
  
 <span data-ttu-id="68267-109">**✓ DO** попробуйте использовать описательные имена параметров, чтобы указать значение по умолчанию использовать более короткие перегрузки.</span><span class="sxs-lookup"><span data-stu-id="68267-109">**✓ DO** try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>  
  
 <span data-ttu-id="68267-110">**X AVOID** произвольного изменения имен параметров в перегрузках.</span><span class="sxs-lookup"><span data-stu-id="68267-110">**X AVOID** arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="68267-111">Если параметр в одной перегрузке представляет тот же ввод как параметр в другую перегрузку, они должны иметь тем же именем.</span><span class="sxs-lookup"><span data-stu-id="68267-111">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>  
  
 <span data-ttu-id="68267-112">**X AVOID** Несогласованная в порядок параметров в перегруженных членов.</span><span class="sxs-lookup"><span data-stu-id="68267-112">**X AVOID** being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="68267-113">Параметры с одинаковым именем должны отображаться в той же позиции в все перегрузки.</span><span class="sxs-lookup"><span data-stu-id="68267-113">Parameters with the same name should appear in the same position in all overloads.</span></span>  
  
 <span data-ttu-id="68267-114">**✓ DO** сделать виртуальной только самую длинную перегрузку (если требуется расширяемость).</span><span class="sxs-lookup"><span data-stu-id="68267-114">**✓ DO** make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="68267-115">Более короткие перегрузки должны просто вызывать через более.</span><span class="sxs-lookup"><span data-stu-id="68267-115">Shorter overloads should simply call through to a longer overload.</span></span>  
  
 <span data-ttu-id="68267-116">**X DO NOT** использовать `ref` или `out` модификаторы для перегрузки членов.</span><span class="sxs-lookup"><span data-stu-id="68267-116">**X DO NOT** use `ref` or `out` modifiers to overload members.</span></span>  
  
 <span data-ttu-id="68267-117">В некоторых языках не удается разрешить вызовы перегрузки следующим образом.</span><span class="sxs-lookup"><span data-stu-id="68267-117">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="68267-118">Кроме того эти перегрузки обычно имеет совершенно другую семантику и, вероятно, не должно быть два отдельных метода перегрузки, но вместо этого.</span><span class="sxs-lookup"><span data-stu-id="68267-118">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>  
  
 <span data-ttu-id="68267-119">**X DO NOT** имеют перегрузки с параметрами в одной позиции и похожих, но различную семантику.</span><span class="sxs-lookup"><span data-stu-id="68267-119">**X DO NOT** have overloads with parameters at the same position and similar types yet with different semantics.</span></span>  
  
 <span data-ttu-id="68267-120">**✓ DO** Разрешить `null` для передачи дополнительных аргументов.</span><span class="sxs-lookup"><span data-stu-id="68267-120">**✓ DO**  allow `null` to be passed for optional arguments.</span></span>  
  
 <span data-ttu-id="68267-121">**✓ DO** использовать член перегрузка предпочтительнее, чем определение членов с аргументами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="68267-121">**✓ DO** use member overloading rather than defining members with default arguments.</span></span>  
  
 <span data-ttu-id="68267-122">Аргументы по умолчанию не являются CLS-совместимым.</span><span class="sxs-lookup"><span data-stu-id="68267-122">Default arguments are not CLS compliant.</span></span>  
  
 <span data-ttu-id="68267-123">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="68267-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="68267-124">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="68267-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68267-125">См. также</span><span class="sxs-lookup"><span data-stu-id="68267-125">See also</span></span>

- [<span data-ttu-id="68267-126">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="68267-126">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="68267-127">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="68267-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
