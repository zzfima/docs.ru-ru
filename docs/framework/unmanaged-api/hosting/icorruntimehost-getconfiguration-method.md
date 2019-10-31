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
ms.openlocfilehash: 87549118742da797ef0dd1b08ae9e72c466f7841
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139574"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="7b61c-102">Метод ICorRuntimeHost::GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="7b61c-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="7b61c-103">Возвращает объект, позволяющий основному приложению указывать конфигурацию обратного вызова среды CLR.</span><span class="sxs-lookup"><span data-stu-id="7b61c-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b61c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b61c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b61c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7b61c-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="7b61c-106">заполняет Указатель на адрес объекта [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) , который может использоваться для настройки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="7b61c-106">[out] A pointer to the address of an [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b61c-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="7b61c-107">Remarks</span></span>  
 <span data-ttu-id="7b61c-108">Прежде чем инициализировать среду CLR, ее необходимо настроить. в противном случае метод `GetConfiguration` возвращает значение HRESULT, указывающее на ошибку.</span><span class="sxs-lookup"><span data-stu-id="7b61c-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b61c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7b61c-109">Requirements</span></span>  
 <span data-ttu-id="7b61c-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b61c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b61c-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7b61c-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7b61c-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7b61c-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7b61c-113">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="7b61c-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b61c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7b61c-114">See also</span></span>

- [<span data-ttu-id="7b61c-115">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="7b61c-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
