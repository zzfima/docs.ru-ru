---
title: Функция GetCLRIdentityManager
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f40100be3ab05c0c8e8a55d48494569424e88371
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637272"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="5fc5f-102">Функция GetCLRIdentityManager</span><span class="sxs-lookup"><span data-stu-id="5fc5f-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="5fc5f-103">Возвращает указатель на интерфейс, позволяющий общеязыковой среды выполнения (CLR) для управления удостоверениями.</span><span class="sxs-lookup"><span data-stu-id="5fc5f-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="5fc5f-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fc5f-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fc5f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5fc5f-105">Syntax</span></span>  
  
```  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5fc5f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5fc5f-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="5fc5f-107">[in] Объект `REFIID` (идентификатор интерфейса), указывающий интерфейс, который нужно получить.</span><span class="sxs-lookup"><span data-stu-id="5fc5f-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="5fc5f-108">Это значение должно быть IID_ICLRAssemblyIdentityManager или IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="5fc5f-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="5fc5f-109">[out] Указатель на адрес любой [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) или [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="5fc5f-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fc5f-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="5fc5f-110">Remarks</span></span>  
 <span data-ttu-id="5fc5f-111">Вызовите [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) функцию, чтобы получить указатель на `GetCLRIdentityManager` функции.</span><span class="sxs-lookup"><span data-stu-id="5fc5f-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fc5f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5fc5f-112">Requirements</span></span>  
 <span data-ttu-id="5fc5f-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fc5f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fc5f-114">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5fc5f-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5fc5f-115">**Библиотека:** "Mscorwks.dll"</span><span class="sxs-lookup"><span data-stu-id="5fc5f-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="5fc5f-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fc5f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fc5f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5fc5f-117">See also</span></span>
- [<span data-ttu-id="5fc5f-118">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="5fc5f-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
