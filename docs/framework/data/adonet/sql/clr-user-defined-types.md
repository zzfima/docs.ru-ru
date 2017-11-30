---
title: "Пользовательские типы CLR"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e81cf54ed9dc516d88b8c7a97c8a5b33b8943d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="db001-102">Пользовательские типы CLR</span><span class="sxs-lookup"><span data-stu-id="db001-102">CLR User-Defined Types</span></span>
<span data-ttu-id="db001-103">Microsoft SQL Server предоставляет поддержку определяемых пользователем типов данных (UDT), реализованную при помощи среды CLR в Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="db001-103">Microsoft SQL Server provides support for user-defined types (UDTs) implemented with the Microsoft .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="db001-104">Среда CLR встроена в SQL Server. Этот механизм позволяет расширять систему типов базы данных.</span><span class="sxs-lookup"><span data-stu-id="db001-104">The CLR is integrated into SQL Server, and this mechanism enables you to extend the type system of the database.</span></span> <span data-ttu-id="db001-105">Определяемые пользователем типы дают возможность расширять систему типов данных SQL Server, а также позволяют определять сложные структурированные типы.</span><span class="sxs-lookup"><span data-stu-id="db001-105">UDTs provide user extensibility of the SQL Server data type system, and also the ability to define complex structured types.</span></span>  
  
 <span data-ttu-id="db001-106">Для архитектуры приложений использование определяемых пользователем типов имеет два основных преимущества.</span><span class="sxs-lookup"><span data-stu-id="db001-106">UDTs can provide two key benefits from an application architecture perspective:</span></span>  
  
-   <span data-ttu-id="db001-107">Строгая инкапсуляция (и на клиенте, и на сервере) между внутренним состоянием и внешней функциональностью.</span><span class="sxs-lookup"><span data-stu-id="db001-107">Strong encapsulation (both in the client and the server) between the internal state and the external behaviors.</span></span>  
  
-   <span data-ttu-id="db001-108">Тесная интеграция между другими связанными функциями сервера.</span><span class="sxs-lookup"><span data-stu-id="db001-108">Deep integration with other related server features.</span></span> <span data-ttu-id="db001-109">После определения собственного типа данных его можно использовать во всех контекстах, где в SQL Server можно использовать системные типы, включая определения столбцов, а также в качестве переменных, параметров, результатов функций, курсоров, триггеров и репликации.</span><span class="sxs-lookup"><span data-stu-id="db001-109">Once you define your own UDT, you can use it in all contexts where you can use a system type in SQL Server, including column definitions, and as variables, parameters, function results, cursors, triggers, and replication.</span></span>  
  
 <span data-ttu-id="db001-110">Более подробные сведения см. в электронной документации по SQL Server для используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="db001-110">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="db001-111">**Электронная документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="db001-111">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="db001-112">Определяемые пользователем типы среды CLR</span><span class="sxs-lookup"><span data-stu-id="db001-112">CLR User-Defined Types</span></span>](http://go.microsoft.com/fwlink/?LinkId=98366)  
  
## <a name="see-also"></a><span data-ttu-id="db001-113">См. также</span><span class="sxs-lookup"><span data-stu-id="db001-113">See Also</span></span>  
 [<span data-ttu-id="db001-114">Создание объектов SQL Server 2005 в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="db001-114">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="db001-115">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="db001-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
