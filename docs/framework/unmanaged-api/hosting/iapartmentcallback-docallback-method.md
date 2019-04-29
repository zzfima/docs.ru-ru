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
ms.openlocfilehash: 77a2ccaf6f972fadd8396378dc7777ec4c85120d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970057"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="56865-102">Метод IApartmentCallback::DoCallback</span><span class="sxs-lookup"><span data-stu-id="56865-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="56865-103">Выполняет указанную функцию в подразделении.</span><span class="sxs-lookup"><span data-stu-id="56865-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56865-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56865-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56865-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="56865-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="56865-106">[in] Указатель на функцию для выполнения в подразделении.</span><span class="sxs-lookup"><span data-stu-id="56865-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="56865-107">[in] Указатель на аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="56865-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56865-108">Требования</span><span class="sxs-lookup"><span data-stu-id="56865-108">Requirements</span></span>  
 <span data-ttu-id="56865-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56865-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56865-110">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="56865-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="56865-111">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="56865-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56865-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56865-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56865-113">См. также</span><span class="sxs-lookup"><span data-stu-id="56865-113">See also</span></span>

- [<span data-ttu-id="56865-114">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="56865-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
