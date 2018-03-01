---
title: "Перечисление HOST_TYPE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a8c910dd06109a8a69f29517812737d4b4dcef21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="hosttype-enumeration"></a><span data-ttu-id="f69f3-102">Перечисление HOST_TYPE</span><span class="sxs-lookup"><span data-stu-id="f69f3-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="f69f3-103">Содержит значения, указывающие тип узла, которое запускает приложение.</span><span class="sxs-lookup"><span data-stu-id="f69f3-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f69f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f69f3-104">Syntax</span></span>  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="f69f3-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f69f3-105">Members</span></span>  
  
|<span data-ttu-id="f69f3-106">Член</span><span class="sxs-lookup"><span data-stu-id="f69f3-106">Member</span></span>|<span data-ttu-id="f69f3-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="f69f3-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="f69f3-108">Запустите приложение от AppLaunch.exe.</span><span class="sxs-lookup"><span data-stu-id="f69f3-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="f69f3-109">Это значение можно используйте для приложений с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="f69f3-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="f69f3-110">Запустите приложение непосредственно.</span><span class="sxs-lookup"><span data-stu-id="f69f3-110">Launch the application directly.</span></span> <span data-ttu-id="f69f3-111">То есть запустите приложение из свой собственный файл .exe.</span><span class="sxs-lookup"><span data-stu-id="f69f3-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="f69f3-112">Это значение можно используйте для приложений с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="f69f3-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="f69f3-113">То же, как HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="f69f3-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f69f3-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f69f3-114">Requirements</span></span>  
 <span data-ttu-id="f69f3-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f69f3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f69f3-116">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f69f3-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f69f3-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f69f3-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f69f3-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f69f3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f69f3-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f69f3-119">See Also</span></span>  
 [<span data-ttu-id="f69f3-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="f69f3-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
