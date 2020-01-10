---
title: Именование параметров
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
ms.openlocfilehash: 0bb67056bb39b6a5f372191a1d0b0bb0dc1fe4d1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709183"
---
# <a name="naming-parameters"></a><span data-ttu-id="a72d7-102">Именование параметров</span><span class="sxs-lookup"><span data-stu-id="a72d7-102">Naming Parameters</span></span>
<span data-ttu-id="a72d7-103">Помимо очевидной причины удобочитаемости, важно следовать рекомендациям по именам параметров, так как параметры отображаются в документации и в конструкторе, когда визуальные средства проектирования предоставляют функции IntelliSense и просмотра классов.</span><span class="sxs-lookup"><span data-stu-id="a72d7-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>  
  
 <span data-ttu-id="a72d7-104">**✓ DO** использовать camelCasing в именах параметров.</span><span class="sxs-lookup"><span data-stu-id="a72d7-104">**✓ DO** use camelCasing in parameter names.</span></span>  
  
 <span data-ttu-id="a72d7-105">**✓ DO** использовать описательные имена параметров.</span><span class="sxs-lookup"><span data-stu-id="a72d7-105">**✓ DO** use descriptive parameter names.</span></span>  
  
 <span data-ttu-id="a72d7-106">**✓ CONSIDER** с помощью имен, основываясь на назначение параметра, а не тип параметра.</span><span class="sxs-lookup"><span data-stu-id="a72d7-106">**✓ CONSIDER** using names based on a parameter’s meaning rather than the parameter’s type.</span></span>  
  
### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="a72d7-107">Именование параметров перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="a72d7-107">Naming Operator Overload Parameters</span></span>  
 <span data-ttu-id="a72d7-108">**✓ DO** использовать `left` и `right` для имен параметров перегрузку бинарного оператора, если нет никакого значения для параметров.</span><span class="sxs-lookup"><span data-stu-id="a72d7-108">**✓ DO** use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="a72d7-109">**✓ DO** использовать `value` унарный оператор перегрузка для имен параметров при наличии не значения для параметров.</span><span class="sxs-lookup"><span data-stu-id="a72d7-109">**✓ DO** use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="a72d7-110">**✓ CONSIDER** значимые имена для оператора перегружать параметров, если это добавляет особого значения.</span><span class="sxs-lookup"><span data-stu-id="a72d7-110">**✓ CONSIDER** meaningful names for operator overload parameters if doing so adds significant value.</span></span>  
  
 <span data-ttu-id="a72d7-111">**X DO NOT** использования сокращений и числовые индексы для оператора перегрузки имена параметров.</span><span class="sxs-lookup"><span data-stu-id="a72d7-111">**X DO NOT** use abbreviations or numeric indices for operator overload parameter names.</span></span>  
  
 <span data-ttu-id="a72d7-112">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="a72d7-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a72d7-113">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="a72d7-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a72d7-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="a72d7-114">See also</span></span>

- [<span data-ttu-id="a72d7-115">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="a72d7-115">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="a72d7-116">Правила именования</span><span class="sxs-lookup"><span data-stu-id="a72d7-116">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
