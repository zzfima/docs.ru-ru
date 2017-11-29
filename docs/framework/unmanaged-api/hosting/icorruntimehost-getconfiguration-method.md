---
title: "Метод ICorRuntimeHost::GetConfiguration"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.GetConfiguration
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61c0a95df2140d2eaf771fcd8f50cd733b9133e1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="ff610-102">Метод ICorRuntimeHost::GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="ff610-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="ff610-103">Возвращает объект, позволяющий основному приложению задать конфигурацию обратного вызова среды common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ff610-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff610-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff610-104">Syntax</span></span>  
  
```  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff610-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ff610-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="ff610-106">[out] Указатель на адрес [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) объект, который можно использовать для настройки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ff610-106">[out] A pointer to the address of an [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff610-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ff610-107">Remarks</span></span>  
 <span data-ttu-id="ff610-108">Среда CLR должен быть настроен до инициализации; в противном случае `GetConfiguration` метод возвращает значение HRESULT, указывающее ошибку.</span><span class="sxs-lookup"><span data-stu-id="ff610-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff610-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ff610-109">Requirements</span></span>  
 <span data-ttu-id="ff610-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff610-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff610-111">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ff610-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff610-112">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff610-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff610-113">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="ff610-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff610-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ff610-114">See Also</span></span>  
 [<span data-ttu-id="ff610-115">ICorRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ff610-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
