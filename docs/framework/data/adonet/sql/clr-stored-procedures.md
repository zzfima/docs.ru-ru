---
title: Хранимые процедуры CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: a1a37ac1257594913c6d06cb08df2882e8773da8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554638"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="1c430-102">Хранимые процедуры CLR</span><span class="sxs-lookup"><span data-stu-id="1c430-102">CLR Stored Procedures</span></span>
<span data-ttu-id="1c430-103">Хранимыми процедурами являются процедуры, которые нельзя использовать в скалярных выражениях.</span><span class="sxs-lookup"><span data-stu-id="1c430-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="1c430-104">Они могут возвращать клиенту табличные результаты и сообщения, вызывать инструкции языка описания данных DDL и языка обработки данных DML, а также возвращать выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="1c430-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c430-105">Microsoft Visual Basic не поддерживает выходные параметры так, как это сделано в Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="1c430-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="1c430-106">Необходимо указать, чтобы передать параметр по ссылке и применить \<Out() > атрибут для представления выходного параметра, как описано ниже:</span><span class="sxs-lookup"><span data-stu-id="1c430-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="1c430-107">Дополнительные сведения см. в разделе версии [документации по SQL Server](/sql) для версии SQL Server, вы используете.</span><span class="sxs-lookup"><span data-stu-id="1c430-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="1c430-108">**Документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="1c430-108">**SQL Server documentation**</span></span>

1. [<span data-ttu-id="1c430-109">Хранимые процедуры CLR</span><span class="sxs-lookup"><span data-stu-id="1c430-109">CLR Stored Procedures</span></span>](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="1c430-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1c430-110">See also</span></span>
- [<span data-ttu-id="1c430-111">Создание объектов SQL Server 2005 в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="1c430-111">Creating SQL Server 2005 Objects In Managed Code</span></span>](https://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)
- [<span data-ttu-id="1c430-112">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1c430-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
