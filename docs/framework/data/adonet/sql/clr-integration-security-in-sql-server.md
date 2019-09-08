---
title: Безопасность интеграции CLR в SQL Server
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: 4756d13ff52a4c55b48c3ea56d26111029c8a7e4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794568"
---
# <a name="clr-integration-security-in-sql-server"></a><span data-ttu-id="e717e-102">Безопасность интеграции CLR в SQL Server</span><span class="sxs-lookup"><span data-stu-id="e717e-102">CLR Integration Security in SQL Server</span></span>
<span data-ttu-id="e717e-103">Microsoft SQL Server обеспечивает интеграцию компонентов среды CLR платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e717e-103">Microsoft SQL Server provides the integration of the common language runtime (CLR) component of the .NET Framework.</span></span> <span data-ttu-id="e717e-104">Интеграция со средой CLR позволяет записывать хранимые процедуры, триггеры, определяемые пользователем типы, определяемые пользователем функции и потоковые возвращающие табличное значение функции, используя любой язык NET Framework, например Microsoft Visual Basic .NET или Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="e717e-104">CLR integration allows you to write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, such as Microsoft Visual Basic .NET or Microsoft Visual C#.</span></span>  
  
 <span data-ttu-id="e717e-105">Среда CLR поддерживает модель безопасности, называемую управлением доступом для кода (CAS).</span><span class="sxs-lookup"><span data-stu-id="e717e-105">The CLR supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="e717e-106">В этой модели разрешения предоставляются сборкам на основе свидетельства, поставляемого кодом в метаданных.</span><span class="sxs-lookup"><span data-stu-id="e717e-106">In this model, permissions are granted to assemblies based on evidence supplied by the code in metadata.</span></span> <span data-ttu-id="e717e-107">SQL Server интегрирует пользовательскую модель безопасности SQL Server с кодом модели безопасности на основе доступа среды CLR.</span><span class="sxs-lookup"><span data-stu-id="e717e-107">SQL Server integrates the user-based security model of SQL Server with the code access-based security model of the CLR.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="e717e-108">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="e717e-108">External Resources</span></span>  
 <span data-ttu-id="e717e-109">Дополнительные сведения об интеграции со средой CLR в SQL Server см. в следующих ресурсах.</span><span class="sxs-lookup"><span data-stu-id="e717e-109">For more information on CLR integration with SQL Server, see the following resources.</span></span>  
  
|<span data-ttu-id="e717e-110">Resource</span><span class="sxs-lookup"><span data-stu-id="e717e-110">Resource</span></span>|<span data-ttu-id="e717e-111">Описание</span><span class="sxs-lookup"><span data-stu-id="e717e-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="e717e-112">Управление доступом для кода</span><span class="sxs-lookup"><span data-stu-id="e717e-112">Code Access Security</span></span>](../../../misc/code-access-security.md)|<span data-ttu-id="e717e-113">Содержит подразделы, описывающие средства CAS на платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e717e-113">Contains topics describing CAS in the .NET Framework.</span></span>|  
|[<span data-ttu-id="e717e-114">Безопасность интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="e717e-114">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)|<span data-ttu-id="e717e-115">Содержит обсуждение модели безопасности для управляемого кода, выполняемого внутри SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e717e-115">Discusses the security model for managed code executing inside of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e717e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e717e-116">See also</span></span>

- [<span data-ttu-id="e717e-117">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e717e-117">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="e717e-118">Сценарии безопасности приложений в SQL Server</span><span class="sxs-lookup"><span data-stu-id="e717e-118">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="e717e-119">Интеграция среды CLR и SQL Server</span><span class="sxs-lookup"><span data-stu-id="e717e-119">SQL Server Common Language Runtime Integration</span></span>](sql-server-common-language-runtime-integration.md)
- [<span data-ttu-id="e717e-120">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e717e-120">ADO.NET Overview</span></span>](../ado-net-overview.md)
