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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110231"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="7c0ef-102">Метод IApartmentCallback::DoCallback</span><span class="sxs-lookup"><span data-stu-id="7c0ef-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="7c0ef-103">Выполняет указанную функцию в подразделении.</span><span class="sxs-lookup"><span data-stu-id="7c0ef-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c0ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c0ef-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c0ef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7c0ef-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="7c0ef-106">[in] Указатель на функцию для выполнения в подразделении.</span><span class="sxs-lookup"><span data-stu-id="7c0ef-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="7c0ef-107">[in] Указатель на аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="7c0ef-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c0ef-108">Требования</span><span class="sxs-lookup"><span data-stu-id="7c0ef-108">Requirements</span></span>  
 <span data-ttu-id="7c0ef-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c0ef-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c0ef-110">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c0ef-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c0ef-111">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c0ef-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="7c0ef-112">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7c0ef-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7c0ef-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7c0ef-113">See also</span></span>

- [<span data-ttu-id="7c0ef-114">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="7c0ef-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
