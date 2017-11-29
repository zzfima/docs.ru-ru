---
title: "Перечисление HOST_TYPE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: HOST_TYPE
api_location: mscoree.dll
api_type: COM
f1_keywords: HOST_TYPE
helpviewer_keywords: HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e191293ff7bde6b1be2210af4e7830fec0d7290d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="hosttype-enumeration"></a><span data-ttu-id="89e18-102">Перечисление HOST_TYPE</span><span class="sxs-lookup"><span data-stu-id="89e18-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="89e18-103">Содержит значения, указывающие тип узла, которое запускает приложение.</span><span class="sxs-lookup"><span data-stu-id="89e18-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89e18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89e18-104">Syntax</span></span>  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="89e18-105">Члены</span><span class="sxs-lookup"><span data-stu-id="89e18-105">Members</span></span>  
  
|<span data-ttu-id="89e18-106">Член</span><span class="sxs-lookup"><span data-stu-id="89e18-106">Member</span></span>|<span data-ttu-id="89e18-107">Описание</span><span class="sxs-lookup"><span data-stu-id="89e18-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="89e18-108">Запустите приложение от AppLaunch.exe.</span><span class="sxs-lookup"><span data-stu-id="89e18-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="89e18-109">Это значение можно используйте для приложений с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="89e18-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="89e18-110">Запустите приложение непосредственно.</span><span class="sxs-lookup"><span data-stu-id="89e18-110">Launch the application directly.</span></span> <span data-ttu-id="89e18-111">То есть запустите приложение из свой собственный файл .exe.</span><span class="sxs-lookup"><span data-stu-id="89e18-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="89e18-112">Это значение можно используйте для приложений с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="89e18-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="89e18-113">То же, как HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="89e18-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="89e18-114">Требования</span><span class="sxs-lookup"><span data-stu-id="89e18-114">Requirements</span></span>  
 <span data-ttu-id="89e18-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89e18-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89e18-116">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="89e18-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89e18-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89e18-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89e18-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89e18-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89e18-119">См. также</span><span class="sxs-lookup"><span data-stu-id="89e18-119">See Also</span></span>  
 [<span data-ttu-id="89e18-120">Перечисления размещения</span><span class="sxs-lookup"><span data-stu-id="89e18-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
