---
title: Метод ICorDebugAppDomain3::GetCachedWinRTTypes
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7d152edac34449a08b4bcfbe5525b63abcba0fb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480771"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="1f7a8-102">Метод ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="1f7a8-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="1f7a8-103">Получает перечислитель для всех кэшированных [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типов.</span><span class="sxs-lookup"><span data-stu-id="1f7a8-103">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f7a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f7a8-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f7a8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f7a8-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="1f7a8-106">[out] Указатель на [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) объект интерфейса, который может перечислить управляемого представления [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типов, загруженных в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="1f7a8-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f7a8-107">Требования</span><span class="sxs-lookup"><span data-stu-id="1f7a8-107">Requirements</span></span>  
 <span data-ttu-id="1f7a8-108">**Платформы:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f7a8-108">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="1f7a8-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f7a8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f7a8-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f7a8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f7a8-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f7a8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f7a8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="1f7a8-112">See also</span></span>
- [<span data-ttu-id="1f7a8-113">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="1f7a8-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
