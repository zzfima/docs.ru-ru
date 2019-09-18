---
title: Надежность
ms.date: 03/30/2017
helpviewer_keywords:
- SQL Server [.NET Framework]
- managed code, reliability
- reliability [.NET Framework]
- writing reliable code
- code, reliability
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: acb84c6617cdffabfe276895f81e7df2b04bb8bb
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046238"
---
# <a name="reliability"></a><span data-ttu-id="0ca03-102">Надежность</span><span class="sxs-lookup"><span data-stu-id="0ca03-102">Reliability</span></span>
<span data-ttu-id="0ca03-103">Крайне важно обеспечить защиту кода, выполняющегося в серверных средах, таких как SQL Server, от асинхронных исключений.</span><span class="sxs-lookup"><span data-stu-id="0ca03-103">It is important that code executing in server environments such as SQL Server protect against asynchronous exceptions.</span></span> <span data-ttu-id="0ca03-104">Вопросы, обсуждаемые в этой статье, относятся не только к SQL Server, но касаются общих принципов написания надежного кода для любого ведущего приложения, выполняющегося в среде .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="0ca03-104">Reliability, as discussed here, is not specific to SQL Server but to writing reliable code for any host executing in a .NET Framework version 2.0 environment.</span></span> <span data-ttu-id="0ca03-105">Тем не менее служба SQL Server приводится в качестве примера, поскольку именно в ней впервые стали широко использоваться новые возможности обеспечения надежности, представленные в версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="0ca03-105">However, SQL Server is the first service making extensive use of the new reliability features of version 2.0, so it is used as an example.</span></span>  
  
 <span data-ttu-id="0ca03-106">В отношении кода, выполняемого в SQL Server, должны действовать более строгие правила надежности, чем для других серверных сред.</span><span class="sxs-lookup"><span data-stu-id="0ca03-106">Code running in SQL Server must deal with more stringent reliability guidelines than other server environments.</span></span> <span data-ttu-id="0ca03-107">Это связано с тем, что SQL Server постоянно функционирует на границе потребления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="0ca03-107">This is due to SQL Server’s steady operation at the edge of resource consumption.</span></span>  <span data-ttu-id="0ca03-108">Исключения <xref:System.OutOfMemoryException> и <xref:System.Threading.ThreadAbortException> встречаются в среде SQL Server достаточно часто.</span><span class="sxs-lookup"><span data-stu-id="0ca03-108"><xref:System.OutOfMemoryException> and <xref:System.Threading.ThreadAbortException> exceptions are not uncommon in the SQL Server environment.</span></span> <span data-ttu-id="0ca03-109">Эти правила в целом ориентированы не столько на обеспечение надежности, сколько на гарантию корректного завершения сбоем полностью доверенного управляемого кода при повторном использовании на уровне <xref:System.AppDomain>, что является основным способом обеспечить согласованность и доступность сервера.</span><span class="sxs-lookup"><span data-stu-id="0ca03-109">These guidelines in general are focused less on reliability and more on allowing fully trusted managed code to fail gracefully in the face of <xref:System.AppDomain>-level recycling, which is the primary way the server maintains consistency and availability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0ca03-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="0ca03-110">In This Section</span></span>  
 [<span data-ttu-id="0ca03-111">Программирование SQL Server и атрибуты защиты ведущего приложения</span><span class="sxs-lookup"><span data-stu-id="0ca03-111">SQL Server Programming and Host Protection Attributes</span></span>](sql-server-programming-and-host-protection-attributes.md)  
 <span data-ttu-id="0ca03-112">Описывает использование атрибута <xref:System.Security.Permissions.HostProtectionAttribute> в SQL Server для ограничения выполнения управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="0ca03-112">Describes how the <xref:System.Security.Permissions.HostProtectionAttribute> attribute is used by SQL Server to restrict the execution of managed code.</span></span>  
  
 [<span data-ttu-id="0ca03-113">Рекомендации по обеспечению надежности</span><span class="sxs-lookup"><span data-stu-id="0ca03-113">Reliability Best Practices</span></span>](reliability-best-practices.md)  
 <span data-ttu-id="0ca03-114">Содержит рекомендации по написанию кода, отвечающего требованиям надежности.</span><span class="sxs-lookup"><span data-stu-id="0ca03-114">Provides guidelines for writing code that meets reliability requirements.</span></span>  
  
 [<span data-ttu-id="0ca03-115">Области ограниченного выполнения</span><span class="sxs-lookup"><span data-stu-id="0ca03-115">Constrained Execution Regions</span></span>](constrained-execution-regions.md)  
 <span data-ttu-id="0ca03-116">Описывает функции и поведения областей ограниченного выполнения (CER).</span><span class="sxs-lookup"><span data-stu-id="0ca03-116">Describes the function and behavior of constrained execution regions (CERs).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0ca03-117">Ссылка</span><span class="sxs-lookup"><span data-stu-id="0ca03-117">Reference</span></span>  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>
