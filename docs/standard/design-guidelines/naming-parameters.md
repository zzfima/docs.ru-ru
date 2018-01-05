---
title: "Именование параметров"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a10fa8835bfbcf826f8a3bb9318966e0dc603864
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="naming-parameters"></a><span data-ttu-id="466df-102">Именование параметров</span><span class="sxs-lookup"><span data-stu-id="466df-102">Naming Parameters</span></span>
<span data-ttu-id="466df-103">Помимо очевидной причине удобочитаемость необходимо придерживаться следующих правил имена параметров, поскольку параметры отображаются в документации и в конструкторе при средства визуального проектирования предоставляют Intellisense и функции просмотра классов.</span><span class="sxs-lookup"><span data-stu-id="466df-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>  
  
 <span data-ttu-id="466df-104">**✓ СДЕЛАТЬ** использовать camelCasing в именах параметров.</span><span class="sxs-lookup"><span data-stu-id="466df-104">**✓ DO** use camelCasing in parameter names.</span></span>  
  
 <span data-ttu-id="466df-105">**✓ СДЕЛАТЬ** использовать описательные имена параметров.</span><span class="sxs-lookup"><span data-stu-id="466df-105">**✓ DO** use descriptive parameter names.</span></span>  
  
 <span data-ttu-id="466df-106">**✓ Попробуйте** с помощью имен, основываясь на назначение параметра, а не тип параметра.</span><span class="sxs-lookup"><span data-stu-id="466df-106">**✓ CONSIDER** using names based on a parameter’s meaning rather than the parameter’s type.</span></span>  
  
### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="466df-107">Именование параметров перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="466df-107">Naming Operator Overload Parameters</span></span>  
 <span data-ttu-id="466df-108">**СДЕЛАТЬ ✓** использовать `left` и `right` для имен параметров перегрузку бинарного оператора, если нет никакого значения для параметров.</span><span class="sxs-lookup"><span data-stu-id="466df-108">**✓ DO** use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="466df-109">**СДЕЛАТЬ ✓** использовать `value` унарный оператор перегрузка для имен параметров при наличии не значения для параметров.</span><span class="sxs-lookup"><span data-stu-id="466df-109">**✓ DO** use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="466df-110">**✓ Попробуйте** значимые имена для оператора перегружать параметров, если это добавляет особого значения.</span><span class="sxs-lookup"><span data-stu-id="466df-110">**✓ CONSIDER** meaningful names for operator overload parameters if doing so adds significant value.</span></span>  
  
 <span data-ttu-id="466df-111">**X не** использования сокращений и числовые индексы для оператора перегрузки имена параметров.</span><span class="sxs-lookup"><span data-stu-id="466df-111">**X DO NOT** use abbreviations or numeric indices for operator overload parameter names.</span></span>  
  
 <span data-ttu-id="466df-112">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="466df-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="466df-113">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="466df-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="466df-114">См. также</span><span class="sxs-lookup"><span data-stu-id="466df-114">See Also</span></span>  
 [<span data-ttu-id="466df-115">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="466df-115">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="466df-116">Правила именования</span><span class="sxs-lookup"><span data-stu-id="466df-116">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
