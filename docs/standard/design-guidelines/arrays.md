---
title: Массивы
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ac7e28c3172f2ed68d402e1d04a1664644c7f25
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46288242"
---
# <a name="arrays"></a><span data-ttu-id="6b40e-102">Массивы</span><span class="sxs-lookup"><span data-stu-id="6b40e-102">Arrays</span></span>
<span data-ttu-id="6b40e-103">**✓ DO** способом с помощью коллекций на массивы в открытых интерфейсах API.</span><span class="sxs-lookup"><span data-stu-id="6b40e-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="6b40e-104">[Коллекций](../../../docs/standard/design-guidelines/guidelines-for-collections.md) разделе содержатся сведения о выборе между коллекций и массивов.</span><span class="sxs-lookup"><span data-stu-id="6b40e-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="6b40e-105">**X DO NOT** использовать поля только для чтения массив.</span><span class="sxs-lookup"><span data-stu-id="6b40e-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="6b40e-106">Само поле только для чтения и не может быть изменено, но можно изменить элементы в массиве.</span><span class="sxs-lookup"><span data-stu-id="6b40e-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="6b40e-107">**✓ CONSIDER** ступенчатые массивы вместо многомерных массивов.</span><span class="sxs-lookup"><span data-stu-id="6b40e-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="6b40e-108">Массив массивов — это массив, содержащий элементы, которые также являются массивами.</span><span class="sxs-lookup"><span data-stu-id="6b40e-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="6b40e-109">Массивы, которые составляют элементы могут иметь различные размеры, что позволяет экономить пространство для некоторых наборов данных (например, разреженных матрицы), по сравнению с многомерных массивов.</span><span class="sxs-lookup"><span data-stu-id="6b40e-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="6b40e-110">Кроме того среда CLR оптимизирует операции с индексами на массивы массивов, поэтому они могут достичь более высокой производительности среды выполнения, в некоторых сценариях.</span><span class="sxs-lookup"><span data-stu-id="6b40e-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="6b40e-111">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="6b40e-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6b40e-112">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="6b40e-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b40e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6b40e-113">See also</span></span>

- <xref:System.Array>  
- [<span data-ttu-id="6b40e-114">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="6b40e-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="6b40e-115">Правила использования</span><span class="sxs-lookup"><span data-stu-id="6b40e-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
