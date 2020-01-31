---
title: Массивы
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: d4a1f379a88231654c710b1df7b505316377c915
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741802"
---
# <a name="arrays"></a><span data-ttu-id="f2d84-102">Массивы</span><span class="sxs-lookup"><span data-stu-id="f2d84-102">Arrays</span></span>
<span data-ttu-id="f2d84-103">✔️ предпочитаете использовать коллекции через массивы в общедоступных API.</span><span class="sxs-lookup"><span data-stu-id="f2d84-103">✔️ DO prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="f2d84-104">Раздел [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) содержит сведения о выборе между коллекциями и массивами.</span><span class="sxs-lookup"><span data-stu-id="f2d84-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>

 <span data-ttu-id="f2d84-105">❌ не использовать поля массива, доступного только для чтения.</span><span class="sxs-lookup"><span data-stu-id="f2d84-105">❌ DO NOT use read-only array fields.</span></span> <span data-ttu-id="f2d84-106">Само поле доступно только для чтения и не может быть изменено, но элементы массива могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="f2d84-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>

 <span data-ttu-id="f2d84-107">✔️ Рассмотрите возможность использования немассивных массивов вместо многомерных массивов.</span><span class="sxs-lookup"><span data-stu-id="f2d84-107">✔️ CONSIDER using jagged arrays instead of multidimensional arrays.</span></span>

 <span data-ttu-id="f2d84-108">Массив массива — это массив с элементами, которые также являются массивами.</span><span class="sxs-lookup"><span data-stu-id="f2d84-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="f2d84-109">Массивы, составляющие элементы, могут иметь разные размеры, что приводит к уменьшению объема незанятого пространства для некоторых наборов данных (например, разреженной матрицы) по сравнению с многомерными массивами.</span><span class="sxs-lookup"><span data-stu-id="f2d84-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="f2d84-110">Более того, среда CLR оптимизирует операции с индексами на массивах массива, чтобы они могли улучшить производительность во время выполнения в некоторых сценариях.</span><span class="sxs-lookup"><span data-stu-id="f2d84-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>

 <span data-ttu-id="f2d84-111">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="f2d84-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="f2d84-112">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="f2d84-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="f2d84-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="f2d84-113">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="f2d84-114">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="f2d84-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="f2d84-115">Правила использования</span><span class="sxs-lookup"><span data-stu-id="f2d84-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
