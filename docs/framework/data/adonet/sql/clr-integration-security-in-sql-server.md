---
title: "Безопасность интеграции CLR в SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 37437d827fc0ff6583178f33f4cceaa86f5175dd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="clr-integration-security-in-sql-server"></a><span data-ttu-id="21965-102">Безопасность интеграции CLR в SQL Server</span><span class="sxs-lookup"><span data-stu-id="21965-102">CLR Integration Security in SQL Server</span></span>
<span data-ttu-id="21965-103">Microsoft SQL Server обеспечивает интеграцию компонентов среды CLR платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="21965-103">Microsoft SQL Server provides the integration of the common language runtime (CLR) component of the .NET Framework.</span></span> <span data-ttu-id="21965-104">Интеграция со средой CLR позволяет записывать хранимые процедуры, триггеры, определяемые пользователем типы, определяемые пользователем функции и потоковые возвращающие табличное значение функции, используя любой язык NET Framework, например Microsoft Visual Basic .NET или Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="21965-104">CLR integration allows you to write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, such as Microsoft Visual Basic .NET or Microsoft Visual C#.</span></span>  
  
 <span data-ttu-id="21965-105">Среда CLR поддерживает модель безопасности, называемую управлением доступом для кода (CAS).</span><span class="sxs-lookup"><span data-stu-id="21965-105">The CLR supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="21965-106">В этой модели разрешения предоставляются сборкам на основе свидетельства, поставляемого кодом в метаданных.</span><span class="sxs-lookup"><span data-stu-id="21965-106">In this model, permissions are granted to assemblies based on evidence supplied by the code in metadata.</span></span> <span data-ttu-id="21965-107">SQL Server интегрирует пользовательскую модель безопасности SQL Server с кодом модели безопасности на основе доступа среды CLR.</span><span class="sxs-lookup"><span data-stu-id="21965-107">SQL Server integrates the user-based security model of SQL Server with the code access-based security model of the CLR.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="21965-108">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="21965-108">External Resources</span></span>  
 <span data-ttu-id="21965-109">Дополнительные сведения об интеграции со средой CLR в SQL Server см. в следующих ресурсах.</span><span class="sxs-lookup"><span data-stu-id="21965-109">For more information on CLR integration with SQL Server, see the following resources.</span></span>  
  
|<span data-ttu-id="21965-110">Ресурс</span><span class="sxs-lookup"><span data-stu-id="21965-110">Resource</span></span>|<span data-ttu-id="21965-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="21965-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="21965-112">Управление доступом для кода</span><span class="sxs-lookup"><span data-stu-id="21965-112">Code Access Security</span></span>](http://msdn.microsoft.com/library/23a20143-241d-4fe5-9d9f-3933fd594c03)|<span data-ttu-id="21965-113">Содержит подразделы, описывающие средства CAS на платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="21965-113">Contains topics describing CAS in the .NET Framework.</span></span>|  
|[<span data-ttu-id="21965-114">Безопасность интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="21965-114">CLR Integration Security</span></span>](http://go.microsoft.com/fwlink/?LinkId=59998)|<span data-ttu-id="21965-115">Содержит обсуждение модели безопасности для управляемого кода, выполняемого внутри SQL Server.</span><span class="sxs-lookup"><span data-stu-id="21965-115">Discusses the security model for managed code executing inside of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21965-116">См. также</span><span class="sxs-lookup"><span data-stu-id="21965-116">See Also</span></span>  
 [<span data-ttu-id="21965-117">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="21965-117">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="21965-118">Сценарии безопасности приложений в SQL Server</span><span class="sxs-lookup"><span data-stu-id="21965-118">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="21965-119">Интеграция среды CLR и SQL Server</span><span class="sxs-lookup"><span data-stu-id="21965-119">SQL Server Common Language Runtime Integration</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 [<span data-ttu-id="21965-120">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="21965-120">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
