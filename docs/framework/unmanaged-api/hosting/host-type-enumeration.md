---
title: Перечисление HOST_TYPE
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfb1cff3e95c5ff86d22913745b7d14982766b48
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175231"
---
# <a name="hosttype-enumeration"></a><span data-ttu-id="e26e6-102">Перечисление HOST_TYPE</span><span class="sxs-lookup"><span data-stu-id="e26e6-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="e26e6-103">Содержит значения, указывающие тип узла, которое запускает приложение.</span><span class="sxs-lookup"><span data-stu-id="e26e6-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e26e6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e26e6-104">Syntax</span></span>  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="e26e6-105">Участники</span><span class="sxs-lookup"><span data-stu-id="e26e6-105">Members</span></span>  
  
|<span data-ttu-id="e26e6-106">Член</span><span class="sxs-lookup"><span data-stu-id="e26e6-106">Member</span></span>|<span data-ttu-id="e26e6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e26e6-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="e26e6-108">Запустите приложение из AppLaunch.exe.</span><span class="sxs-lookup"><span data-stu-id="e26e6-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="e26e6-109">Используйте это значение для частично доверенных приложениях.</span><span class="sxs-lookup"><span data-stu-id="e26e6-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="e26e6-110">Запустите приложение напрямую.</span><span class="sxs-lookup"><span data-stu-id="e26e6-110">Launch the application directly.</span></span> <span data-ttu-id="e26e6-111">То есть запуска приложения из свой собственный файл .exe.</span><span class="sxs-lookup"><span data-stu-id="e26e6-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="e26e6-112">Это значение используется для приложений с полным уровнем доверия.</span><span class="sxs-lookup"><span data-stu-id="e26e6-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="e26e6-113">Совпадает со значением HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="e26e6-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e26e6-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e26e6-114">Requirements</span></span>  
 <span data-ttu-id="e26e6-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e26e6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e26e6-116">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e26e6-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e26e6-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e26e6-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e26e6-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e26e6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e26e6-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e26e6-119">See also</span></span>

- [<span data-ttu-id="e26e6-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="e26e6-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
