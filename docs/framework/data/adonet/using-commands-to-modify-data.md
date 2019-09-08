---
title: Использование команд для изменения данных
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: 34c73549f18cd4bebb8caf842b252828b7f0a185
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780561"
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="12ade-102">Использование команд для изменения данных</span><span class="sxs-lookup"><span data-stu-id="12ade-102">Using Commands to Modify Data</span></span>
<span data-ttu-id="12ade-103">Используя поставщик данных .NET Framework, можно выполнять хранимые процедуры или инструкции языка описания данных DDL (например, CREATE TABLE и ALTER COLUMN) для выполнения операций со схемой в базе данных или в каталоге.</span><span class="sxs-lookup"><span data-stu-id="12ade-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="12ade-104">Эти команды не возвращают строки в виде запроса, поэтому объект **Command** предоставляет **ExecuteNonQuery** для их обработки.</span><span class="sxs-lookup"><span data-stu-id="12ade-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="12ade-105">Кроме использования функции **ExecuteNonQuery** для изменения схемы, этот метод можно также использовать для обработки инструкций SQL, которые изменяют данные, но не возвращают строки, такие как INSERT, Update и DELETE.</span><span class="sxs-lookup"><span data-stu-id="12ade-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="12ade-106">Хотя метод **ExecuteNonQuery** не возвращает строки, входные и выходные параметры и возвращаемые значения могут передаваться и возвращаться через коллекцию **Parameters** объекта **Command** .</span><span class="sxs-lookup"><span data-stu-id="12ade-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="12ade-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="12ade-107">In This Section</span></span>  
 [<span data-ttu-id="12ade-108">Обновление данных в источнике данных</span><span class="sxs-lookup"><span data-stu-id="12ade-108">Updating Data in a Data Source</span></span>](updating-data-in-a-data-source.md)  
 <span data-ttu-id="12ade-109">Описывает выполнение команд или хранимых процедур, которые изменяют данные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="12ade-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="12ade-110">Выполнение операций каталога</span><span class="sxs-lookup"><span data-stu-id="12ade-110">Performing Catalog Operations</span></span>](performing-catalog-operations.md)  
 <span data-ttu-id="12ade-111">Описывает выполнение команд, которые изменяют схему базы данных.</span><span class="sxs-lookup"><span data-stu-id="12ade-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12ade-112">См. также</span><span class="sxs-lookup"><span data-stu-id="12ade-112">See also</span></span>

- [<span data-ttu-id="12ade-113">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="12ade-113">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="12ade-114">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="12ade-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="12ade-115">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="12ade-115">ADO.NET Overview</span></span>](ado-net-overview.md)
