---
title: Безопасность интеграции CLR в SQL Server
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: 946401211d515df9ba5b9e38d7cfd10730973b64
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165819"
---
# <a name="clr-integration-security-in-sql-server"></a><span data-ttu-id="897b0-102">Безопасность интеграции CLR в SQL Server</span><span class="sxs-lookup"><span data-stu-id="897b0-102">CLR Integration Security in SQL Server</span></span>
<span data-ttu-id="897b0-103">Microsoft SQL Server обеспечивает интеграцию компонентов среды CLR платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="897b0-103">Microsoft SQL Server provides the integration of the common language runtime (CLR) component of the .NET Framework.</span></span> <span data-ttu-id="897b0-104">Интеграция со средой CLR позволяет записывать хранимые процедуры, триггеры, определяемые пользователем типы, определяемые пользователем функции и потоковые возвращающие табличное значение функции, используя любой язык NET Framework, например Microsoft Visual Basic .NET или Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="897b0-104">CLR integration allows you to write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, such as Microsoft Visual Basic .NET or Microsoft Visual C#.</span></span>  
  
 <span data-ttu-id="897b0-105">Среда CLR поддерживает модель безопасности, называемую управлением доступом для кода (CAS).</span><span class="sxs-lookup"><span data-stu-id="897b0-105">The CLR supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="897b0-106">В этой модели разрешения предоставляются сборкам на основе свидетельства, поставляемого кодом в метаданных.</span><span class="sxs-lookup"><span data-stu-id="897b0-106">In this model, permissions are granted to assemblies based on evidence supplied by the code in metadata.</span></span> <span data-ttu-id="897b0-107">SQL Server интегрирует пользовательскую модель безопасности SQL Server с кодом модели безопасности на основе доступа среды CLR.</span><span class="sxs-lookup"><span data-stu-id="897b0-107">SQL Server integrates the user-based security model of SQL Server with the code access-based security model of the CLR.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="897b0-108">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="897b0-108">External Resources</span></span>  
 <span data-ttu-id="897b0-109">Дополнительные сведения об интеграции со средой CLR в SQL Server см. в следующих ресурсах.</span><span class="sxs-lookup"><span data-stu-id="897b0-109">For more information on CLR integration with SQL Server, see the following resources.</span></span>  
  
|<span data-ttu-id="897b0-110">Ресурс</span><span class="sxs-lookup"><span data-stu-id="897b0-110">Resource</span></span>|<span data-ttu-id="897b0-111">Описание</span><span class="sxs-lookup"><span data-stu-id="897b0-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="897b0-112">Управление доступом для кода</span><span class="sxs-lookup"><span data-stu-id="897b0-112">Code Access Security</span></span>](../../../../../docs/framework/misc/code-access-security.md)|<span data-ttu-id="897b0-113">Содержит подразделы, описывающие средства CAS на платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="897b0-113">Contains topics describing CAS in the .NET Framework.</span></span>|  
|[<span data-ttu-id="897b0-114">Безопасность интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="897b0-114">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)|<span data-ttu-id="897b0-115">Содержит обсуждение модели безопасности для управляемого кода, выполняемого внутри SQL Server.</span><span class="sxs-lookup"><span data-stu-id="897b0-115">Discusses the security model for managed code executing inside of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="897b0-116">См. также</span><span class="sxs-lookup"><span data-stu-id="897b0-116">See also</span></span>

- [<span data-ttu-id="897b0-117">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="897b0-117">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [<span data-ttu-id="897b0-118">Сценарии безопасности приложений в SQL Server</span><span class="sxs-lookup"><span data-stu-id="897b0-118">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="897b0-119">Интеграция среды CLR и SQL Server</span><span class="sxs-lookup"><span data-stu-id="897b0-119">SQL Server Common Language Runtime Integration</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)
- [<span data-ttu-id="897b0-120">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="897b0-120">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)
