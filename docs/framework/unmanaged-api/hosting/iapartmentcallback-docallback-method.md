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
ms.openlocfilehash: 9bb257a3d84d5022b9ae13c89a34572485d3033b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126944"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="f76ed-102">Метод IApartmentCallback::DoCallback</span><span class="sxs-lookup"><span data-stu-id="f76ed-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="f76ed-103">Выполняет указанную функцию в апартаменте.</span><span class="sxs-lookup"><span data-stu-id="f76ed-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f76ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f76ed-104">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f76ed-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f76ed-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="f76ed-106">окне Указатель на функцию, которая должна быть выполнена в апартаменте.</span><span class="sxs-lookup"><span data-stu-id="f76ed-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="f76ed-107">окне Указатель на аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="f76ed-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f76ed-108">Требования</span><span class="sxs-lookup"><span data-stu-id="f76ed-108">Requirements</span></span>  
 <span data-ttu-id="f76ed-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f76ed-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f76ed-110">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f76ed-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f76ed-111">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f76ed-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f76ed-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f76ed-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f76ed-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f76ed-113">See also</span></span>

- [<span data-ttu-id="f76ed-114">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="f76ed-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
