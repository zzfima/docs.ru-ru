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
ms.openlocfilehash: e18172ecf2d4300ae42cc42ecdb1783744cac105
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490415"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="83b92-102">Функция GetCLRIdentityManager</span><span class="sxs-lookup"><span data-stu-id="83b92-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="83b92-103">Возвращает указатель на интерфейс, позволяющий общеязыковой среды выполнения (CLR) для управления удостоверениями.</span><span class="sxs-lookup"><span data-stu-id="83b92-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="83b92-104">Эта функция является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="83b92-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83b92-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83b92-105">Syntax</span></span>  
  
```  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83b92-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="83b92-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="83b92-107">[in] Объект `REFIID` (идентификатор интерфейса), указывающий интерфейс, который нужно получить.</span><span class="sxs-lookup"><span data-stu-id="83b92-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="83b92-108">Это значение должно быть IID_ICLRAssemblyIdentityManager или IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="83b92-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="83b92-109">[out] Указатель на адрес любой [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) или [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="83b92-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83b92-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="83b92-110">Remarks</span></span>  
 <span data-ttu-id="83b92-111">Вызовите [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) функцию, чтобы получить указатель на `GetCLRIdentityManager` функции.</span><span class="sxs-lookup"><span data-stu-id="83b92-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83b92-112">Требования</span><span class="sxs-lookup"><span data-stu-id="83b92-112">Requirements</span></span>  
 <span data-ttu-id="83b92-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83b92-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83b92-114">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="83b92-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83b92-115">**Библиотека:** "Mscorwks.dll"</span><span class="sxs-lookup"><span data-stu-id="83b92-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="83b92-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83b92-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b92-117">См. также</span><span class="sxs-lookup"><span data-stu-id="83b92-117">See also</span></span>

- [<span data-ttu-id="83b92-118">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="83b92-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
