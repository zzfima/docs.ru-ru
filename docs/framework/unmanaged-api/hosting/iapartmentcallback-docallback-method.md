---
title: "Метод IApartmentCallback::DoCallback"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 06aaab6d4ad7d33bbdc52a38c999cc925eee1666
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="f398b-102">Метод IApartmentCallback::DoCallback</span><span class="sxs-lookup"><span data-stu-id="f398b-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="f398b-103">Выполняет заданную функцию в подразделении.</span><span class="sxs-lookup"><span data-stu-id="f398b-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f398b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f398b-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f398b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f398b-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="f398b-106">[in] Указатель на функцию для выполнения в подразделении.</span><span class="sxs-lookup"><span data-stu-id="f398b-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="f398b-107">[in] Указатель на аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="f398b-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f398b-108">Требования</span><span class="sxs-lookup"><span data-stu-id="f398b-108">Requirements</span></span>  
 <span data-ttu-id="f398b-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f398b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f398b-110">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f398b-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f398b-111">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f398b-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f398b-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f398b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f398b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f398b-113">See Also</span></span>  
 [<span data-ttu-id="f398b-114">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="f398b-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
