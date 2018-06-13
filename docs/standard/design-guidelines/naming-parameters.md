---
title: Именование параметров
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed6b96bb05c52de4bfd8b6ad6b972c9d22ca66da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570491"
---
# <a name="naming-parameters"></a><span data-ttu-id="ee8a2-102">Именование параметров</span><span class="sxs-lookup"><span data-stu-id="ee8a2-102">Naming Parameters</span></span>
<span data-ttu-id="ee8a2-103">Помимо очевидной причине удобочитаемость необходимо придерживаться следующих правил имена параметров, поскольку параметры отображаются в документации и в конструкторе при средства визуального проектирования предоставляют Intellisense и функции просмотра классов.</span><span class="sxs-lookup"><span data-stu-id="ee8a2-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>  
  
 <span data-ttu-id="ee8a2-104">**✓ СДЕЛАТЬ** использовать camelCasing в именах параметров.</span><span class="sxs-lookup"><span data-stu-id="ee8a2-104">**✓ DO** use camelCasing in parameter names.</span></span>  
  
 <span data-ttu-id="ee8a2-105">**✓ СДЕЛАТЬ** использовать описательные имена параметров.</span><span class="sxs-lookup"><span data-stu-id="ee8a2-105">**✓ DO** use descriptive parameter names.</span></span>  
  
 <span data-ttu-id="ee8a2-106">**✓ Попробуйте** с помощью имен, основываясь на назначение параметра, а не тип параметра.</span><span class="sxs-lookup"><span data-stu-id="ee8a2-106">**✓ CONSIDER** using names based on a parameter’s meaning rather than the parameter’s type.</span></span>  
  
### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="ee8a2-107">Именование параметров перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="ee8a2-107">Naming Operator Overload Parameters</span></span>  
 <span data-ttu-id="ee8a2-108">**СДЕЛАТЬ ✓** использовать `left` и `right` для имен параметров перегрузку бинарного оператора, если нет никакого значения для параметров.</span><span class="sxs-lookup"><span data-stu-id="ee8a2-108">**✓ DO** use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="ee8a2-109">**СДЕЛАТЬ ✓** использовать `value` унарный оператор перегрузка для имен параметров при наличии не значения для параметров.</span><span class="sxs-lookup"><span data-stu-id="ee8a2-109">**✓ DO** use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="ee8a2-110">**✓ Попробуйте** значимые имена для оператора перегружать параметров, если это добавляет особого значения.</span><span class="sxs-lookup"><span data-stu-id="ee8a2-110">**✓ CONSIDER** meaningful names for operator overload parameters if doing so adds significant value.</span></span>  
  
 <span data-ttu-id="ee8a2-111">**X не** использования сокращений и числовые индексы для оператора перегрузки имена параметров.</span><span class="sxs-lookup"><span data-stu-id="ee8a2-111">**X DO NOT** use abbreviations or numeric indices for operator overload parameter names.</span></span>  
  
 <span data-ttu-id="ee8a2-112">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="ee8a2-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ee8a2-113">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="ee8a2-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee8a2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ee8a2-114">See Also</span></span>  
 [<span data-ttu-id="ee8a2-115">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="ee8a2-115">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="ee8a2-116">Правила именования</span><span class="sxs-lookup"><span data-stu-id="ee8a2-116">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
