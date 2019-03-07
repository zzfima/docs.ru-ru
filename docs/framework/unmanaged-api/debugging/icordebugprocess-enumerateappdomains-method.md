---
title: Метод ICorDebugProcess::EnumerateAppDomains
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnumerateAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnumerateAppDomains
helpviewer_keywords:
- ICorDebugProcess::EnumerateAppDomains method [.NET Framework debugging]
- EnumerateAppDomains method [.NET Framework debugging]
ms.assetid: d508981f-e2b2-445b-a649-69951c22702d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02e051d311e447475bea724b0bd7420ee8b590f6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495732"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="bf9fb-102">Метод ICorDebugProcess::EnumerateAppDomains</span><span class="sxs-lookup"><span data-stu-id="bf9fb-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="bf9fb-103">Перечисляет все домены приложений в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="bf9fb-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf9fb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf9fb-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf9fb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf9fb-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="bf9fb-106">[out] Указатель на адрес [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) то есть перечислитель для доменов приложений в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="bf9fb-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf9fb-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="bf9fb-107">Remarks</span></span>  
 <span data-ttu-id="bf9fb-108">Этот метод можно использовать перед [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="bf9fb-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf9fb-109">Требования</span><span class="sxs-lookup"><span data-stu-id="bf9fb-109">Requirements</span></span>  
 <span data-ttu-id="bf9fb-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf9fb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf9fb-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf9fb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf9fb-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf9fb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf9fb-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf9fb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
