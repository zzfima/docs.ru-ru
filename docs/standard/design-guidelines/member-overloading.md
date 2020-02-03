---
title: Перегрузка членов
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
ms.openlocfilehash: c9cb178e838aab99c22089b527a6bd2e86b325de
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727842"
---
# <a name="member-overloading"></a><span data-ttu-id="2213e-102">Перегрузка членов</span><span class="sxs-lookup"><span data-stu-id="2213e-102">Member Overloading</span></span>
<span data-ttu-id="2213e-103">Перегрузка членов означает создание двух или более членов одного типа, которые отличаются только числом или типом параметров, но имеют одинаковые имена.</span><span class="sxs-lookup"><span data-stu-id="2213e-103">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="2213e-104">Например, в следующем примере метод `WriteLine` перегружен:</span><span class="sxs-lookup"><span data-stu-id="2213e-104">For example, in the following, the `WriteLine` method is overloaded:</span></span>

```csharp
public static class Console {
    public void WriteLine();
    public void WriteLine(string value);
    public void WriteLine(bool value);
    ...
}
```

 <span data-ttu-id="2213e-105">Поскольку только методы, конструкторы и индексированные свойства могут иметь параметры, только эти члены могут быть перегружены.</span><span class="sxs-lookup"><span data-stu-id="2213e-105">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>

 <span data-ttu-id="2213e-106">Перегрузка является одним из наиболее важных методов для повышения удобства использования, производительности и удобочитаемости многократно используемых библиотек.</span><span class="sxs-lookup"><span data-stu-id="2213e-106">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="2213e-107">Перегрузка по количеству параметров позволяет предоставить более простые версии конструкторов и методов.</span><span class="sxs-lookup"><span data-stu-id="2213e-107">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="2213e-108">Перегрузка типа параметра позволяет использовать одно и то же имя элемента для членов, выполняющих идентичные операции с выбранным набором различных типов.</span><span class="sxs-lookup"><span data-stu-id="2213e-108">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>

 <span data-ttu-id="2213e-109">✔️ попытаться использовать описательные имена параметров, чтобы указать значение по умолчанию, используемое более короткими перегрузками.</span><span class="sxs-lookup"><span data-stu-id="2213e-109">✔️ DO try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>

 <span data-ttu-id="2213e-110">❌ избежать произвольного изменения имен параметров в перегрузках.</span><span class="sxs-lookup"><span data-stu-id="2213e-110">❌ AVOID arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="2213e-111">Если параметр в одной перегрузке представляет те же входные данные, что и параметр в другой перегрузке, параметры должны иметь одинаковые имена.</span><span class="sxs-lookup"><span data-stu-id="2213e-111">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>

 <span data-ttu-id="2213e-112">❌ избежать несоответствия в упорядочении параметров в перегруженных членах.</span><span class="sxs-lookup"><span data-stu-id="2213e-112">❌ AVOID being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="2213e-113">Параметры с одинаковым именем должны отображаться в одной и той же области во всех перегрузках.</span><span class="sxs-lookup"><span data-stu-id="2213e-113">Parameters with the same name should appear in the same position in all overloads.</span></span>

 <span data-ttu-id="2213e-114">✔️ сделать только самую длинную виртуальную перегрузку (если требуется расширяемость).</span><span class="sxs-lookup"><span data-stu-id="2213e-114">✔️ DO make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="2213e-115">Более короткие перегрузки должны просто вызывать более длинную перегрузку.</span><span class="sxs-lookup"><span data-stu-id="2213e-115">Shorter overloads should simply call through to a longer overload.</span></span>

 <span data-ttu-id="2213e-116">❌ не используйте модификаторы `ref` или `out` для перегрузки членов.</span><span class="sxs-lookup"><span data-stu-id="2213e-116">❌ DO NOT use `ref` or `out` modifiers to overload members.</span></span>

 <span data-ttu-id="2213e-117">Некоторые языки не могут разрешать вызовы перегрузок следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2213e-117">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="2213e-118">Кроме того, такие перегрузки обычно имеют совершенно другую семантику и, вероятно, не должны перегружаться, но вместо этого можно использовать два отдельных метода.</span><span class="sxs-lookup"><span data-stu-id="2213e-118">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>

 <span data-ttu-id="2213e-119">❌ не имеют перегрузок с параметрами в той же позиции и аналогичных типов, но с разной семантикой.</span><span class="sxs-lookup"><span data-stu-id="2213e-119">❌ DO NOT have overloads with parameters at the same position and similar types yet with different semantics.</span></span>

 <span data-ttu-id="2213e-120">✔️ Разрешить передачу `null` для необязательных аргументов.</span><span class="sxs-lookup"><span data-stu-id="2213e-120">✔️ DO  allow `null` to be passed for optional arguments.</span></span>

 <span data-ttu-id="2213e-121">✔️ использовать перегрузку членов вместо определения членов с аргументами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2213e-121">✔️ DO use member overloading rather than defining members with default arguments.</span></span>

 <span data-ttu-id="2213e-122">Аргументы по умолчанию несовместимы с CLS.</span><span class="sxs-lookup"><span data-stu-id="2213e-122">Default arguments are not CLS compliant.</span></span>

 <span data-ttu-id="2213e-123">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="2213e-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="2213e-124">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="2213e-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="2213e-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2213e-125">See also</span></span>

- [<span data-ttu-id="2213e-126">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="2213e-126">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="2213e-127">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="2213e-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
