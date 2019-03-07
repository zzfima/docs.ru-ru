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
ms.openlocfilehash: ea711cc03716f4cd0a06a96208da942a69f36d66
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471684"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="82674-102">Функция GetCLRIdentityManager</span><span class="sxs-lookup"><span data-stu-id="82674-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="82674-103">Возвращает указатель на интерфейс, позволяющий общеязыковой среды выполнения (CLR) для управления удостоверениями.</span><span class="sxs-lookup"><span data-stu-id="82674-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="82674-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82674-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82674-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82674-105">Syntax</span></span>  
  
```  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82674-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="82674-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="82674-107">[in] Объект `REFIID` (идентификатор интерфейса), указывающий интерфейс, который нужно получить.</span><span class="sxs-lookup"><span data-stu-id="82674-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="82674-108">Это значение должно быть IID_ICLRAssemblyIdentityManager или IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="82674-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="82674-109">[out] Указатель на адрес любой [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) или [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="82674-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82674-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="82674-110">Remarks</span></span>  
 <span data-ttu-id="82674-111">Вызовите [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) функцию, чтобы получить указатель на `GetCLRIdentityManager` функции.</span><span class="sxs-lookup"><span data-stu-id="82674-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82674-112">Требования</span><span class="sxs-lookup"><span data-stu-id="82674-112">Requirements</span></span>  
 <span data-ttu-id="82674-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82674-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82674-114">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="82674-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82674-115">**Библиотека:** "Mscorwks.dll"</span><span class="sxs-lookup"><span data-stu-id="82674-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="82674-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82674-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82674-117">См. также</span><span class="sxs-lookup"><span data-stu-id="82674-117">See also</span></span>
- [<span data-ttu-id="82674-118">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="82674-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
