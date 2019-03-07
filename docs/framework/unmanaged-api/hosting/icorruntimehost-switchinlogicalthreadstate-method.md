---
title: Метод ICorRuntimeHost::SwitchInLogicalThreadState
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d12555fb53a6c1b21f161402da77860adcf0a4b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478912"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="b4b34-102">Метод ICorRuntimeHost::SwitchInLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="b4b34-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="b4b34-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="b4b34-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4b34-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4b34-104">Syntax</span></span>  
  
```  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4b34-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4b34-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="b4b34-106">[in] Файл cookie, который указывает волокон для использования.</span><span class="sxs-lookup"><span data-stu-id="b4b34-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4b34-107">Требования</span><span class="sxs-lookup"><span data-stu-id="b4b34-107">Requirements</span></span>  
 <span data-ttu-id="b4b34-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4b34-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4b34-109">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b4b34-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4b34-110">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4b34-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4b34-111">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="b4b34-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4b34-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b4b34-112">See also</span></span>
- [<span data-ttu-id="b4b34-113">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b4b34-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
