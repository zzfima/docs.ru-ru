---
title: Хранимые процедуры CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: c02efa3f0a91d176b626761335bd2d5a2b96b966
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917956"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="466b4-102">Хранимые процедуры CLR</span><span class="sxs-lookup"><span data-stu-id="466b4-102">CLR Stored Procedures</span></span>
<span data-ttu-id="466b4-103">Хранимыми процедурами являются процедуры, которые нельзя использовать в скалярных выражениях.</span><span class="sxs-lookup"><span data-stu-id="466b4-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="466b4-104">Они могут возвращать клиенту табличные результаты и сообщения, вызывать инструкции языка описания данных DDL и языка обработки данных DML, а также возвращать выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="466b4-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="466b4-105">Microsoft Visual Basic не поддерживает выходные параметры так, как это сделано в Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="466b4-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="466b4-106">Необходимо указать, чтобы передать параметр по ссылке, и применить \<атрибут Out () > для представления выходного параметра, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="466b4-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="466b4-107">Более подробные сведения см. в версии [SQL Server документации](/sql) по используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="466b4-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="466b4-108">**Документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="466b4-108">**SQL Server documentation**</span></span>

1. [<span data-ttu-id="466b4-109">Хранимые процедуры CLR</span><span class="sxs-lookup"><span data-stu-id="466b4-109">CLR Stored Procedures</span></span>](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="466b4-110">См. также</span><span class="sxs-lookup"><span data-stu-id="466b4-110">See also</span></span>

- <span data-ttu-id="466b4-111">[Создание объектов SQL Server 2005 в управляемом коде](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="466b4-111">[Creating SQL Server 2005 Objects In Managed Code](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span></span>
- [<span data-ttu-id="466b4-112">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="466b4-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
