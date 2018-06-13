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
ms.openlocfilehash: 782a6cf70aa3e3446d8da3160712d57245afe176
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405529"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="ab374-102">Метод ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="ab374-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="ab374-103">Возвращает перечислитель для всех кэшированных [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типов.</span><span class="sxs-lookup"><span data-stu-id="ab374-103">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab374-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab374-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab374-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ab374-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="ab374-106">[out] Указатель на [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) объект интерфейса, можно перечислить представления управляемых [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типов, загруженные в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="ab374-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab374-107">Требования</span><span class="sxs-lookup"><span data-stu-id="ab374-107">Requirements</span></span>  
 <span data-ttu-id="ab374-108">**Платформы:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab374-108">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="ab374-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab374-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab374-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab374-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab374-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab374-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab374-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ab374-112">See Also</span></span>  
 [<span data-ttu-id="ab374-113">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="ab374-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
