---
title: Интерфейс IActionOnCLREvent
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24191e93d0d8b27d01a914cae76c9ff4e0a7182d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430786"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="a7eef-102">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="a7eef-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="a7eef-103">Предоставляет [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) метод, который выполняет обратные вызовы для событий, зарегистрированных с помощью вызова [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="a7eef-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7eef-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a7eef-104">Methods</span></span>  
  
|<span data-ttu-id="a7eef-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a7eef-105">Method</span></span>|<span data-ttu-id="a7eef-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a7eef-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7eef-107">Метод OnEvent</span><span class="sxs-lookup"><span data-stu-id="a7eef-107">OnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)|<span data-ttu-id="a7eef-108">Выполняет обратный вызов для зарегистрированного события.</span><span class="sxs-lookup"><span data-stu-id="a7eef-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7eef-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a7eef-109">Requirements</span></span>  
 <span data-ttu-id="a7eef-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7eef-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7eef-111">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7eef-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7eef-112">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7eef-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7eef-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7eef-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7eef-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a7eef-114">See Also</span></span>  
 [<span data-ttu-id="a7eef-115">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="a7eef-115">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="a7eef-116">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="a7eef-116">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="a7eef-117">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="a7eef-117">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="a7eef-118">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="a7eef-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
