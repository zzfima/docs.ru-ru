---
title: Перечисление EMemoryAvailable
ms.date: 03/30/2017
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
ms.openlocfilehash: aec3c5f140df7eab10ea2bfa33634a4d853adcb0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134293"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="1020e-102">Перечисление EMemoryAvailable</span><span class="sxs-lookup"><span data-stu-id="1020e-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="1020e-103">Содержит значения, указывающие объем свободной физической памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1020e-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="1020e-104">Эти значения логически сопоставляются с событиями для высокого и нехватки памяти, возвращаемой функцией `CreateMemoryResourceNotification` в Windows API.</span><span class="sxs-lookup"><span data-stu-id="1020e-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1020e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1020e-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="1020e-106">Члены</span><span class="sxs-lookup"><span data-stu-id="1020e-106">Members</span></span>  
  
|<span data-ttu-id="1020e-107">Член</span><span class="sxs-lookup"><span data-stu-id="1020e-107">Member</span></span>|<span data-ttu-id="1020e-108">Описание</span><span class="sxs-lookup"><span data-stu-id="1020e-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="1020e-109">Доступно достаточно физической памяти.</span><span class="sxs-lookup"><span data-stu-id="1020e-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="1020e-110">Доступно очень мало физической памяти.</span><span class="sxs-lookup"><span data-stu-id="1020e-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="1020e-111">Доступная физическая память не является нейтральной.</span><span class="sxs-lookup"><span data-stu-id="1020e-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1020e-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="1020e-112">Remarks</span></span>  
 <span data-ttu-id="1020e-113">Это значение передается узлом в среду CLR с помощью вызова метода [ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1020e-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1020e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1020e-114">Requirements</span></span>  
 <span data-ttu-id="1020e-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1020e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1020e-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1020e-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1020e-117">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1020e-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1020e-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1020e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1020e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1020e-119">See also</span></span>

- [<span data-ttu-id="1020e-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="1020e-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
