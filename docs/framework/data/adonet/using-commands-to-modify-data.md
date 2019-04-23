---
title: Использование команд для изменения данных
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: f2e3d162bfbdcb79cfecefa4ddc8e6a0dc46ee3c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102457"
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="41c9d-102">Использование команд для изменения данных</span><span class="sxs-lookup"><span data-stu-id="41c9d-102">Using Commands to Modify Data</span></span>
<span data-ttu-id="41c9d-103">Используя поставщик данных .NET Framework, можно выполнять хранимые процедуры или инструкции языка описания данных DDL (например, CREATE TABLE и ALTER COLUMN) для выполнения операций со схемой в базе данных или в каталоге.</span><span class="sxs-lookup"><span data-stu-id="41c9d-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="41c9d-104">Эти команды не возвращают строки, как запрос, поэтому **команда** предоставляет **ExecuteNonQuery** для их обработки.</span><span class="sxs-lookup"><span data-stu-id="41c9d-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="41c9d-105">Помимо использования **ExecuteNonQuery** для изменения схемы, можно также использовать этот метод для обработки инструкций SQL, которые изменяют данные, но не возвращают строки, например INSERT, UPDATE и удаления.</span><span class="sxs-lookup"><span data-stu-id="41c9d-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="41c9d-106">Несмотря на то, что строки не возвращаются таблицей **ExecuteNonQuery** метод, входные и выходные параметры и возвращаемые значения могут передаваться и возвращаться через **параметры** коллекцию **команды**  объекта.</span><span class="sxs-lookup"><span data-stu-id="41c9d-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="41c9d-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="41c9d-107">In This Section</span></span>  
 [<span data-ttu-id="41c9d-108">Обновление данных в источнике данных</span><span class="sxs-lookup"><span data-stu-id="41c9d-108">Updating Data in a Data Source</span></span>](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 <span data-ttu-id="41c9d-109">Описывает выполнение команд или хранимых процедур, которые изменяют данные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="41c9d-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="41c9d-110">Выполнение операций каталога</span><span class="sxs-lookup"><span data-stu-id="41c9d-110">Performing Catalog Operations</span></span>](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 <span data-ttu-id="41c9d-111">Описывает выполнение команд, которые изменяют схему базы данных.</span><span class="sxs-lookup"><span data-stu-id="41c9d-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41c9d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="41c9d-112">See also</span></span>

- [<span data-ttu-id="41c9d-113">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="41c9d-113">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="41c9d-114">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="41c9d-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="41c9d-115">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="41c9d-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
