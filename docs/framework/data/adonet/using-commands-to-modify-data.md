---
title: "Использование команд для изменения данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 853f8e4e75df3fffad4a2d5ecd4f7ae21b5d674f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="2e7e4-102">Использование команд для изменения данных</span><span class="sxs-lookup"><span data-stu-id="2e7e4-102">Using Commands to Modify Data</span></span>
<span data-ttu-id="2e7e4-103">Используя поставщик данных .NET Framework, можно выполнять хранимые процедуры или инструкции языка описания данных DDL (например, CREATE TABLE и ALTER COLUMN) для выполнения операций со схемой в базе данных или в каталоге.</span><span class="sxs-lookup"><span data-stu-id="2e7e4-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="2e7e4-104">Эти команды не возвращают строки отличие от запросов, поэтому **команда** объект предоставляет **ExecuteNonQuery** их обработать.</span><span class="sxs-lookup"><span data-stu-id="2e7e4-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="2e7e4-105">Помимо использования **ExecuteNonQuery** для изменения схемы, можно также использовать этот метод для обработки инструкций SQL, которые изменяют данные, но не возвращают строки, таких как вставки, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="2e7e4-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="2e7e4-106">Несмотря на то, что строки не возвращаются **ExecuteNonQuery** метод, входные и выходные параметры и возвращаемые значения могут передаваться и возвращаться через **параметры** коллекцию **команды**  объекта.</span><span class="sxs-lookup"><span data-stu-id="2e7e4-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2e7e4-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="2e7e4-107">In This Section</span></span>  
 [<span data-ttu-id="2e7e4-108">Обновление данных в источнике данных</span><span class="sxs-lookup"><span data-stu-id="2e7e4-108">Updating Data in a Data Source</span></span>](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 <span data-ttu-id="2e7e4-109">Описывает выполнение команд или хранимых процедур, которые изменяют данные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="2e7e4-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="2e7e4-110">Выполнение операций каталога</span><span class="sxs-lookup"><span data-stu-id="2e7e4-110">Performing Catalog Operations</span></span>](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 <span data-ttu-id="2e7e4-111">Описывает выполнение команд, которые изменяют схему базы данных.</span><span class="sxs-lookup"><span data-stu-id="2e7e4-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e7e4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="2e7e4-112">See Also</span></span>  
 [<span data-ttu-id="2e7e4-113">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2e7e4-113">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="2e7e4-114">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="2e7e4-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="2e7e4-115">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2e7e4-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
