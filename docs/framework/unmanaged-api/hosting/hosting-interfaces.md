---
title: Интерфейсы размещения
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e330e0d06077d1eef63cf44f31bbcbf7c3431b59
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985547"
---
# <a name="hosting-interfaces"></a><span data-ttu-id="2cb9b-102">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="2cb9b-102">Hosting Interfaces</span></span>
<span data-ttu-id="2cb9b-103">В этом разделе описываются интерфейсы, которые неуправляемые узлы могут использовать для интеграции общеязыковой среды выполнения (CLR) в свои приложения.</span><span class="sxs-lookup"><span data-stu-id="2cb9b-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="2cb9b-104">Интерфейсы размещения платформы .NET Framework версии 2.0 заменяют собой интерфейсов платформы .NET Framework версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="2cb9b-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="2cb9b-105">Существуют значительные различия между двумя наборами интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="2cb9b-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="2cb9b-106">Смешивание их могло вызвать неожиданное поведение и не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="2cb9b-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="2cb9b-107">.NET Framework версий 3.0 и 3.5 используют интерфейсы размещения платформы .NET Framework версии 2.0 и не предоставляет дополнительные функции размещения.</span><span class="sxs-lookup"><span data-stu-id="2cb9b-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="2cb9b-108">[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] Интерфейсы размещения заменяют интерфейсы платформы .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="2cb9b-108">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="2cb9b-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="2cb9b-109">In This Section</span></span>  
 [<span data-ttu-id="2cb9b-110">Устаревшие интерфейсы размещения CLR и коклассы</span><span class="sxs-lookup"><span data-stu-id="2cb9b-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="2cb9b-111">Описание размещения интерфейсов, доступных в .NET Framework версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="2cb9b-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="2cb9b-112">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="2cb9b-112">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="2cb9b-113">Описание размещения интерфейсов, доступных в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="2cb9b-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="2cb9b-114">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="2cb9b-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="2cb9b-115">Описание размещения интерфейсов, доступных в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cb9b-115">Describes the hosting interfaces introduced in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2cb9b-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="2cb9b-116">Related Sections</span></span>  
 [<span data-ttu-id="2cb9b-117">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="2cb9b-117">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="2cb9b-118">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="2cb9b-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="2cb9b-119">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="2cb9b-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
  
 [<span data-ttu-id="2cb9b-120">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="2cb9b-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
  
 [<span data-ttu-id="2cb9b-121">Размещение</span><span class="sxs-lookup"><span data-stu-id="2cb9b-121">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
  
 <span data-ttu-id="2cb9b-122">[Хост-приложения среды выполнения](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2cb9b-122">[Runtime Hosts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>
