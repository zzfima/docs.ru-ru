---
title: Типизированные наборы данных
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 7c8111e0e62a57b6745a5ea0387fc65a05839df8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785839"
---
# <a name="typed-datasets"></a><span data-ttu-id="0e4c9-102">Типизированные наборы данных</span><span class="sxs-lookup"><span data-stu-id="0e4c9-102">Typed DataSets</span></span>
<span data-ttu-id="0e4c9-103">Наряду с доступом к значениям с поздним связыванием через слабо типизированные переменные, в объекте <xref:System.Data.DataSet> предоставляется доступ к данным на основе принципа строгой типизации.</span><span class="sxs-lookup"><span data-stu-id="0e4c9-103">Along with late bound access to values through weakly typed variables, the <xref:System.Data.DataSet> provides access to data through a strongly typed metaphor.</span></span> <span data-ttu-id="0e4c9-104">Доступ к таблицам и столбцам, которые являются частью **набора данных** , можно получить с помощью понятных имен и строго типизированных переменных.</span><span class="sxs-lookup"><span data-stu-id="0e4c9-104">Tables and columns that are part of the **DataSet** can be accessed using user-friendly names and strongly typed variables.</span></span>  
  
 <span data-ttu-id="0e4c9-105">Типизированный **набор данных** — это класс, производный от **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="0e4c9-105">A typed **DataSet** is a class that derives from a **DataSet**.</span></span> <span data-ttu-id="0e4c9-106">Таким образом, он наследует все методы, события и свойства **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="0e4c9-106">As such, it inherits all the methods, events, and properties of a **DataSet**.</span></span> <span data-ttu-id="0e4c9-107">Кроме того, типизированный **набор данных** предоставляет строго типизированные методы, события и свойства.</span><span class="sxs-lookup"><span data-stu-id="0e4c9-107">Additionally, a typed **DataSet** provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="0e4c9-108">Это означает, что к таблицам и столбцам можно обращаться путем указания имен вместо использования методов на основе коллекций.</span><span class="sxs-lookup"><span data-stu-id="0e4c9-108">This means you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="0e4c9-109">Помимо улучшенной удобочитаемости кода, типизированный **набор данных** также позволяет редактору кода Visual Studio .NET автоматически завершать строки по мере ввода.</span><span class="sxs-lookup"><span data-stu-id="0e4c9-109">Aside from the improved readability of the code, a typed **DataSet** also allows the Visual Studio .NET code editor to automatically complete lines as you type.</span></span>  
  
 <span data-ttu-id="0e4c9-110">Кроме того, строго типизированный **набор данных** предоставляет доступ к значениям в качестве правильного типа во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="0e4c9-110">Additionally, the strongly typed **DataSet** provides access to values as the correct type at compile time.</span></span> <span data-ttu-id="0e4c9-111">При использовании строго типизированного **набора данных**ошибки несоответствия типов перехватываются при компиляции кода, а не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0e4c9-111">With a strongly typed **DataSet**, type mismatch errors are caught when the code is compiled rather than at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0e4c9-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="0e4c9-112">In This Section</span></span>  
 [<span data-ttu-id="0e4c9-113">Создание объектов DataSet со строгой типизацией</span><span class="sxs-lookup"><span data-stu-id="0e4c9-113">Generating Strongly Typed DataSets</span></span>](generating-strongly-typed-datasets.md)  
 <span data-ttu-id="0e4c9-114">Описывает создание и использование строго типизированного **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="0e4c9-114">Describes how to create and use a strongly typed **DataSet**.</span></span>  
  
 [<span data-ttu-id="0e4c9-115">Добавление заметок к типизированным объектам DataSet</span><span class="sxs-lookup"><span data-stu-id="0e4c9-115">Annotating Typed DataSets</span></span>](annotating-typed-datasets.md)  
 <span data-ttu-id="0e4c9-116">Описывает, как закомментировать схему XSD, используемую для создания строго типизированного **набора данных**, чтобы предоставить понятные имена элементам **набора данных** без изменения базовой схемы.</span><span class="sxs-lookup"><span data-stu-id="0e4c9-116">Describes how to annotate the XML Schema definition language (XSD) schema used to generate a strongly typed **DataSet**, to give **DataSet** elements friendly names without altering the underlying schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e4c9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0e4c9-117">See also</span></span>

- [<span data-ttu-id="0e4c9-118">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="0e4c9-118">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="0e4c9-119">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0e4c9-119">ADO.NET Overview</span></span>](../ado-net-overview.md)
