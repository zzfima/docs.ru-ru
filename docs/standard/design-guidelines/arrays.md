---
title: "Массивы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2e634cdcff0b1b2968a3b64d8d05cb57feeddb51
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="arrays"></a><span data-ttu-id="c2375-102">Массивы</span><span class="sxs-lookup"><span data-stu-id="c2375-102">Arrays</span></span>
<span data-ttu-id="c2375-103">**✓ СДЕЛАТЬ** способом с помощью коллекций на массивы в открытых интерфейсах API.</span><span class="sxs-lookup"><span data-stu-id="c2375-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="c2375-104">[Коллекций](../../../docs/standard/design-guidelines/guidelines-for-collections.md) разделе содержатся сведения о выборе между коллекциям и массивам.</span><span class="sxs-lookup"><span data-stu-id="c2375-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="c2375-105">**X не** использовать поля только для чтения массив.</span><span class="sxs-lookup"><span data-stu-id="c2375-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="c2375-106">Поле доступно только для чтения и не может быть изменен, но можно изменить элементы в массиве.</span><span class="sxs-lookup"><span data-stu-id="c2375-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="c2375-107">**✓ Попробуйте** ступенчатые массивы вместо многомерных массивов.</span><span class="sxs-lookup"><span data-stu-id="c2375-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="c2375-108">Массив массивов — это массив с элементами, которые также являются массивами.</span><span class="sxs-lookup"><span data-stu-id="c2375-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="c2375-109">Массивы, которые составляют элементы могут иметь различные размеры, что позволяет экономить пространство для некоторых наборов данных (например, Разреженные матрицы) по сравнению с многомерных массивов.</span><span class="sxs-lookup"><span data-stu-id="c2375-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="c2375-110">Кроме того среда CLR оптимизирует операции с индексами на массивы массивов, поэтому они могут достичь высокой производительности среды выполнения, в некоторых сценариях.</span><span class="sxs-lookup"><span data-stu-id="c2375-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="c2375-111">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="c2375-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c2375-112">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="c2375-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2375-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c2375-113">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="c2375-114">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="c2375-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="c2375-115">Правила использования</span><span class="sxs-lookup"><span data-stu-id="c2375-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
