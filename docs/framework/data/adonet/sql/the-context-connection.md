---
title: "Подключение контекста"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e443ca86-9243-4234-a822-ed10a53a9de0
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9a50f3d91f8de146aee602cc94a33728e5a4c738
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="the-context-connection"></a><span data-ttu-id="90697-102">Подключение контекста</span><span class="sxs-lookup"><span data-stu-id="90697-102">The Context Connection</span></span>
<span data-ttu-id="90697-103">Проблема внутреннего доступа к данным встречается довольно часто.</span><span class="sxs-lookup"><span data-stu-id="90697-103">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="90697-104">Речь идет о тех ситуациях, когда необходимо получить доступ к тому же серверу, на котором выполняется конкретная хранимая процедура или функция среды CLR.</span><span class="sxs-lookup"><span data-stu-id="90697-104">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="90697-105">Один из вариантов состоит в том, чтобы создать соединение с использованием <xref:System.Data.SqlClient.SqlConnection>, задать строку соединения, в которой указан локальный сервер, и открыть соединение.</span><span class="sxs-lookup"><span data-stu-id="90697-105">One option is to create a connection using <xref:System.Data.SqlClient.SqlConnection>, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="90697-106">В этом случае необходимо указать учетные данные для входа.</span><span class="sxs-lookup"><span data-stu-id="90697-106">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="90697-107">К тому же соединение устанавливается в другом сеансе базы данных (по сравнению с хранимой процедурой или функцией), может иметь другие параметры `SET`, находиться в отдельной транзакции, не позволять обнаруживать используемые временные таблицы и т. д.</span><span class="sxs-lookup"><span data-stu-id="90697-107">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="90697-108">Если управляемая хранимая процедура или функция выполняется в процессе SQL Server, причина этого состоит в том, что какой-то пользователь подключился к этому серверу и выполнил инструкцию SQL для вызова соответствующего кода.</span><span class="sxs-lookup"><span data-stu-id="90697-108">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="90697-109">В этой ситуации можно обеспечить выполнение хранимой процедуры или функции в контексте данного соединения вместе с осуществляемой в нем транзакцией, параметрами `SET` и т. д.</span><span class="sxs-lookup"><span data-stu-id="90697-109">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="90697-110">В этом состоит так называемое контекстное соединение.</span><span class="sxs-lookup"><span data-stu-id="90697-110">This is called the context connection.</span></span>  
  
 <span data-ttu-id="90697-111">Контекстное соединение позволяет выполнять инструкции Transact-SQL в том же контексте, в каком первоначально был вызван конкретный код.</span><span class="sxs-lookup"><span data-stu-id="90697-111">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="90697-112">Более подробные сведения см. в электронной документации по SQL Server для используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="90697-112">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="90697-113">**Электронная документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="90697-113">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="90697-114">Подключение контекста</span><span class="sxs-lookup"><span data-stu-id="90697-114">The Context Connection</span></span>](http://go.microsoft.com/fwlink/?LinkId=115395)  
  
## <a name="see-also"></a><span data-ttu-id="90697-115">См. также</span><span class="sxs-lookup"><span data-stu-id="90697-115">See Also</span></span>  
 [<span data-ttu-id="90697-116">Создание объектов SQL Server 2005 в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="90697-116">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="90697-117">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="90697-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
