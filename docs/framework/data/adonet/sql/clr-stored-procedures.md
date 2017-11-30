---
title: "Хранимые процедуры CLR"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1e55222c16d223a86e1e11ce2b985ec0f4d8eaa3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="e4122-102">Хранимые процедуры CLR</span><span class="sxs-lookup"><span data-stu-id="e4122-102">CLR Stored Procedures</span></span>
<span data-ttu-id="e4122-103">Хранимыми процедурами являются процедуры, которые нельзя использовать в скалярных выражениях.</span><span class="sxs-lookup"><span data-stu-id="e4122-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="e4122-104">Они могут возвращать клиенту табличные результаты и сообщения, вызывать инструкции языка описания данных DDL и языка обработки данных DML, а также возвращать выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="e4122-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4122-105">Microsoft Visual Basic не поддерживает выходные параметры так, как это сделано в Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="e4122-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="e4122-106">Необходимо указать, чтобы передать параметр по ссылке и применить \<Out() > атрибут для представления выходного параметра, как описано ниже:</span><span class="sxs-lookup"><span data-stu-id="e4122-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```  
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```  
  
 <span data-ttu-id="e4122-107">Более подробные сведения см. в электронной документации по SQL Server для используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4122-107">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="e4122-108">**Электронная документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="e4122-108">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="e4122-109">Хранимые процедуры CLR</span><span class="sxs-lookup"><span data-stu-id="e4122-109">CLR Stored Procedures</span></span>](http://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="e4122-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e4122-110">See Also</span></span>  
 [<span data-ttu-id="e4122-111">Создание объектов SQL Server 2005 в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="e4122-111">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="e4122-112">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e4122-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
