---
title: Метод ICorRuntimeHost::GetConfiguration
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf74da6eb0e7ce0215023a9a58d6b88c57c4fe8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097342"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="68d29-102">Метод ICorRuntimeHost::GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="68d29-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="68d29-103">Возвращает объект, который позволяет основному приложению задавать конфигурацию обратного вызова для общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="68d29-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68d29-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68d29-104">Syntax</span></span>  
  
```  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68d29-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="68d29-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="68d29-106">[out] Указатель на адрес [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) объект, который можно использовать для настройки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="68d29-106">[out] A pointer to the address of an [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68d29-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="68d29-107">Remarks</span></span>  
 <span data-ttu-id="68d29-108">Среда CLR должен быть настроен до инициализации; в противном случае `GetConfiguration` метод возвращает значение HRESULT, указывающее, произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="68d29-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68d29-109">Требования</span><span class="sxs-lookup"><span data-stu-id="68d29-109">Requirements</span></span>  
 <span data-ttu-id="68d29-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68d29-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68d29-111">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="68d29-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68d29-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="68d29-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68d29-113">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="68d29-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68d29-114">См. также</span><span class="sxs-lookup"><span data-stu-id="68d29-114">See also</span></span>

- [<span data-ttu-id="68d29-115">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="68d29-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
