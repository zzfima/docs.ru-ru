---
title: Метод IApartmentCallback::DoCallback
ms.date: 03/30/2017
api_name:
- IApartmentCallback.DoCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7bd983a41307a4244b5426b8f6b997569cd631e9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770506"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="cd974-102">Метод IApartmentCallback::DoCallback</span><span class="sxs-lookup"><span data-stu-id="cd974-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="cd974-103">Выполняет указанную функцию в подразделении.</span><span class="sxs-lookup"><span data-stu-id="cd974-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd974-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd974-104">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd974-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cd974-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="cd974-106">[in] Указатель на функцию для выполнения в подразделении.</span><span class="sxs-lookup"><span data-stu-id="cd974-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="cd974-107">[in] Указатель на аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="cd974-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd974-108">Требования</span><span class="sxs-lookup"><span data-stu-id="cd974-108">Requirements</span></span>  
 <span data-ttu-id="cd974-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd974-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd974-110">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cd974-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd974-111">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cd974-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd974-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd974-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd974-113">См. также</span><span class="sxs-lookup"><span data-stu-id="cd974-113">See also</span></span>

- [<span data-ttu-id="cd974-114">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="cd974-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
