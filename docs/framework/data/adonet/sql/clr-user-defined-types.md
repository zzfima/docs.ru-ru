---
title: Пользовательские типы CLR
ms.date: 03/30/2017
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
ms.openlocfilehash: 4ea415a348375c52e42ddf26ea09a74e7de5e355
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44177345"
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="fb4fb-102">Пользовательские типы CLR</span><span class="sxs-lookup"><span data-stu-id="fb4fb-102">CLR User-Defined Types</span></span>
<span data-ttu-id="fb4fb-103">Microsoft SQL Server предоставляет поддержку определяемых пользователем типов данных (UDT), реализованную при помощи среды CLR в Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fb4fb-103">Microsoft SQL Server provides support for user-defined types (UDTs) implemented with the Microsoft .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="fb4fb-104">Среда CLR встроена в SQL Server. Этот механизм позволяет расширять систему типов базы данных.</span><span class="sxs-lookup"><span data-stu-id="fb4fb-104">The CLR is integrated into SQL Server, and this mechanism enables you to extend the type system of the database.</span></span> <span data-ttu-id="fb4fb-105">Определяемые пользователем типы дают возможность расширять систему типов данных SQL Server, а также позволяют определять сложные структурированные типы.</span><span class="sxs-lookup"><span data-stu-id="fb4fb-105">UDTs provide user extensibility of the SQL Server data type system, and also the ability to define complex structured types.</span></span>  
  
 <span data-ttu-id="fb4fb-106">Для архитектуры приложений использование определяемых пользователем типов имеет два основных преимущества.</span><span class="sxs-lookup"><span data-stu-id="fb4fb-106">UDTs can provide two key benefits from an application architecture perspective:</span></span>  
  
-   <span data-ttu-id="fb4fb-107">Строгая инкапсуляция (и на клиенте, и на сервере) между внутренним состоянием и внешней функциональностью.</span><span class="sxs-lookup"><span data-stu-id="fb4fb-107">Strong encapsulation (both in the client and the server) between the internal state and the external behaviors.</span></span>  
  
-   <span data-ttu-id="fb4fb-108">Тесная интеграция между другими связанными функциями сервера.</span><span class="sxs-lookup"><span data-stu-id="fb4fb-108">Deep integration with other related server features.</span></span> <span data-ttu-id="fb4fb-109">После определения собственного типа данных его можно использовать во всех контекстах, где в SQL Server можно использовать системные типы, включая определения столбцов, а также в качестве переменных, параметров, результатов функций, курсоров, триггеров и репликации.</span><span class="sxs-lookup"><span data-stu-id="fb4fb-109">Once you define your own UDT, you can use it in all contexts where you can use a system type in SQL Server, including column definitions, and as variables, parameters, function results, cursors, triggers, and replication.</span></span>  
  
 <span data-ttu-id="fb4fb-110">Дополнительные сведения см. в разделе [документации по SQL Server](/sql) для версии SQL Server, вы используете.</span><span class="sxs-lookup"><span data-stu-id="fb4fb-110">For more detailed information, see the [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="fb4fb-111">**Документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="fb4fb-111">**SQL Server documentation**</span></span>
  
1. [<span data-ttu-id="fb4fb-112">Определяемые пользователем типы CLR</span><span class="sxs-lookup"><span data-stu-id="fb4fb-112">CLR User-Defined Types</span></span>](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="see-also"></a><span data-ttu-id="fb4fb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="fb4fb-113">See also</span></span>  

[<span data-ttu-id="fb4fb-114">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fb4fb-114">ADO.NET Overview</span></span>](../ado-net-overview.md)  