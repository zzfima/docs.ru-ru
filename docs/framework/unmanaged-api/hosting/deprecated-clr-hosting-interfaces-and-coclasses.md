---
title: "Устаревшие интерфейсы размещения CLR и CoClasses"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 1
- .NET Framework 1.1, hosting interfaces
- hosting interfaces [.NET Framework], version 1
- .NET Framework 1.0, hosting interfaces
ms.assetid: 7b3d2755-cbab-4160-bc69-eb85791e38c7
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4714183eb79a25639dae6824a1d27eb1ca6bb009
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="deprecated-clr-hosting-interfaces-and-coclasses"></a><span data-ttu-id="fb802-102">Устаревшие интерфейсы размещения CLR и CoClasses</span><span class="sxs-lookup"><span data-stu-id="fb802-102">Deprecated CLR Hosting Interfaces and Coclasses</span></span>
<span data-ttu-id="fb802-103">В этом разделе описываются интерфейсы, которые неуправляемые узлов можно использовать для интеграции общеязыковой среды выполнения (CLR) в .NET Framework версий 1.0 и 1.1 в свои приложения.</span><span class="sxs-lookup"><span data-stu-id="fb802-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the .NET Framework versions 1.0 and 1.1 into their applications.</span></span> <span data-ttu-id="fb802-104">Эти интерфейсы обеспечивают методы для узла, для настройки и загрузки среды выполнения в процесс.</span><span class="sxs-lookup"><span data-stu-id="fb802-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fb802-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="fb802-105">In This Section</span></span>  
 <span data-ttu-id="fb802-106">IAppDomainSetup</span><span class="sxs-lookup"><span data-stu-id="fb802-106">IAppDomainSetup</span></span>  
 <span data-ttu-id="fb802-107">Предоставляет методы для настройки узла <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="fb802-107">Provides methods for the host to configure an <xref:System.AppDomain>.</span></span>  
  
 [<span data-ttu-id="fb802-108">ICeeFileGen-класс</span><span class="sxs-lookup"><span data-stu-id="fb802-108">ICeeFileGen Class</span></span>](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)  
 <span data-ttu-id="fb802-109">(Устарело) Предоставляет функциональные возможности для создания собственного переносимый исполняемый файл (PE).</span><span class="sxs-lookup"><span data-stu-id="fb802-109">(Deprecated) Provides functionality for creating a native portable executable (PE) file.</span></span>  
  
 [<span data-ttu-id="fb802-110">ICorRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="fb802-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 <span data-ttu-id="fb802-111">Предоставляет методы для настройки параметров среды CLR узла.</span><span class="sxs-lookup"><span data-stu-id="fb802-111">Provides methods for the host to configure CLR settings.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fb802-112">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="fb802-112">Related Sections</span></span>  
 [<span data-ttu-id="fb802-113">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="fb802-113">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="fb802-114">Содержит разделы, описывающие размещения интерфейсов, предоставляемых в .NET Framework версии 2.0 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="fb802-114">Contains topics that describe the hosting interfaces provided with the .NET Framework version 2.0 and later versions.</span></span>
