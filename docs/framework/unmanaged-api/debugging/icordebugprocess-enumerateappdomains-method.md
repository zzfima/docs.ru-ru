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
ms.openlocfilehash: 4489238df05edef384b4073ee738a184ff8809ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178674"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="e6a64-102">Метод ICorDebugProcess::EnumerateAppDomains</span><span class="sxs-lookup"><span data-stu-id="e6a64-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="e6a64-103">Перечисляет все области приложений в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="e6a64-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6a64-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6a64-104">Syntax</span></span>  
  
``` cpp
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6a64-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6a64-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="e6a64-106">(ваут) Указатель на адрес [ICorDebugAppDomainEnum,](icordebugappdomainenum-interface.md) который является регистратором для доменов приложений в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="e6a64-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6a64-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e6a64-107">Remarks</span></span>  
 <span data-ttu-id="e6a64-108">Этот метод можно использовать до [вызова ICorDebugManagedCallback::CreateProcess.](icordebugmanagedcallback-createprocess-method.md)</span><span class="sxs-lookup"><span data-stu-id="e6a64-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6a64-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e6a64-109">Requirements</span></span>  
 <span data-ttu-id="e6a64-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6a64-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6a64-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6a64-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6a64-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6a64-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6a64-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6a64-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
