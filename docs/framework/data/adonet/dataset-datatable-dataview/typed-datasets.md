---
title: "Типизированные наборы данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e3d5edc4f469b59ff787e500ad447fe0076c332c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="typed-datasets"></a><span data-ttu-id="c1667-102">Типизированные наборы данных</span><span class="sxs-lookup"><span data-stu-id="c1667-102">Typed DataSets</span></span>
<span data-ttu-id="c1667-103">Наряду с доступом к значениям с поздним связыванием через слабо типизированные переменные, в объекте <xref:System.Data.DataSet> предоставляется доступ к данным на основе принципа строгой типизации.</span><span class="sxs-lookup"><span data-stu-id="c1667-103">Along with late bound access to values through weakly typed variables, the <xref:System.Data.DataSet> provides access to data through a strongly typed metaphor.</span></span> <span data-ttu-id="c1667-104">Таблицы и столбцы, которые являются частью **набора данных** может осуществляться с использованием понятных имен и строго типизированных переменных.</span><span class="sxs-lookup"><span data-stu-id="c1667-104">Tables and columns that are part of the **DataSet** can be accessed using user-friendly names and strongly typed variables.</span></span>  
  
 <span data-ttu-id="c1667-105">Типизированный **DataSet** — это класс, производный от **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="c1667-105">A typed **DataSet** is a class that derives from a **DataSet**.</span></span> <span data-ttu-id="c1667-106">Таким образом, он наследует все методы, события и свойства **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="c1667-106">As such, it inherits all the methods, events, and properties of a **DataSet**.</span></span> <span data-ttu-id="c1667-107">Кроме того, типизированный **DataSet** предоставляет строго типизированные методы, события и свойства.</span><span class="sxs-lookup"><span data-stu-id="c1667-107">Additionally, a typed **DataSet** provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="c1667-108">Это означает, что к таблицам и столбцам можно обращаться путем указания имен вместо использования методов на основе коллекций.</span><span class="sxs-lookup"><span data-stu-id="c1667-108">This means you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="c1667-109">Помимо повышения понятности кода, типизированный **DataSet** позволяет редактор для автоматического завершения строк при вводе кода Visual Studio .NET.</span><span class="sxs-lookup"><span data-stu-id="c1667-109">Aside from the improved readability of the code, a typed **DataSet** also allows the Visual Studio .NET code editor to automatically complete lines as you type.</span></span>  
  
 <span data-ttu-id="c1667-110">Кроме того, строго типизированные **DataSet** предоставляет доступ к значениям правильных типов во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="c1667-110">Additionally, the strongly typed **DataSet** provides access to values as the correct type at compile time.</span></span> <span data-ttu-id="c1667-111">Благодаря использованию строго типизированного **набора данных**, ошибки несоответствия типов выявляются при компилируется код, а не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c1667-111">With a strongly typed **DataSet**, type mismatch errors are caught when the code is compiled rather than at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1667-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="c1667-112">In This Section</span></span>  
 [<span data-ttu-id="c1667-113">Создание строго типизированных наборов данных</span><span class="sxs-lookup"><span data-stu-id="c1667-113">Generating Strongly Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 <span data-ttu-id="c1667-114">Описывает способы создания и использования строго типизированного **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="c1667-114">Describes how to create and use a strongly typed **DataSet**.</span></span>  
  
 [<span data-ttu-id="c1667-115">Создание примечаний к типизированным наборам данных</span><span class="sxs-lookup"><span data-stu-id="c1667-115">Annotating Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 <span data-ttu-id="c1667-116">Описание добавления заметок к схему языка определения схемы XML используется для создания строго типизированного **DataSet**, что позволяет присваивать **набора данных** элементы понятные имена без изменения базовой схемы.</span><span class="sxs-lookup"><span data-stu-id="c1667-116">Describes how to annotate the XML Schema definition language (XSD) schema used to generate a strongly typed **DataSet**, to give **DataSet** elements friendly names without altering the underlying schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1667-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c1667-117">See Also</span></span>  
 [<span data-ttu-id="c1667-118">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="c1667-118">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="c1667-119">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c1667-119">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
