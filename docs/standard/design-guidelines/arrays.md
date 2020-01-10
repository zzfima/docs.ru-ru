---
title: Массивы
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: ac4b073d2d3291922498a0e56c7e81f7e7868c65
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709573"
---
# <a name="arrays"></a><span data-ttu-id="869f1-102">Массивы</span><span class="sxs-lookup"><span data-stu-id="869f1-102">Arrays</span></span>
<span data-ttu-id="869f1-103">**✓ DO** способом с помощью коллекций на массивы в открытых интерфейсах API.</span><span class="sxs-lookup"><span data-stu-id="869f1-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="869f1-104">Раздел [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) содержит сведения о выборе между коллекциями и массивами.</span><span class="sxs-lookup"><span data-stu-id="869f1-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="869f1-105">**X DO NOT** использовать поля только для чтения массив.</span><span class="sxs-lookup"><span data-stu-id="869f1-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="869f1-106">Само поле доступно только для чтения и не может быть изменено, но элементы массива могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="869f1-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="869f1-107">**✓ CONSIDER** ступенчатые массивы вместо многомерных массивов.</span><span class="sxs-lookup"><span data-stu-id="869f1-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="869f1-108">Массив массива — это массив с элементами, которые также являются массивами.</span><span class="sxs-lookup"><span data-stu-id="869f1-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="869f1-109">Массивы, составляющие элементы, могут иметь разные размеры, что приводит к уменьшению объема незанятого пространства для некоторых наборов данных (например, разреженной матрицы) по сравнению с многомерными массивами.</span><span class="sxs-lookup"><span data-stu-id="869f1-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="869f1-110">Более того, среда CLR оптимизирует операции с индексами на массивах массива, чтобы они могли улучшить производительность во время выполнения в некоторых сценариях.</span><span class="sxs-lookup"><span data-stu-id="869f1-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="869f1-111">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="869f1-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="869f1-112">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="869f1-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="869f1-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="869f1-113">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="869f1-114">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="869f1-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="869f1-115">Правила использования</span><span class="sxs-lookup"><span data-stu-id="869f1-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
