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
ms.openlocfilehash: e5fd1730bbe5b6f2905691dce41a7f503227534a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179072"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="edb57-102">Метод ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="edb57-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="edb57-103">Получает регистратор для всех кэшированных типов Выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="edb57-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edb57-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="edb57-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="edb57-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="edb57-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="edb57-106">(ваут) Указатель на объект интерфейса [ICorbugDeGuidToTypeEnum,](icordebugguidtotypeenum-interface.md) который может перечислять управляемые представления типов Windows Runtime, загруженные в настоящее время в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="edb57-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edb57-107">Требования</span><span class="sxs-lookup"><span data-stu-id="edb57-107">Requirements</span></span>  
 <span data-ttu-id="edb57-108">**Платформы:** Время выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="edb57-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="edb57-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="edb57-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="edb57-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edb57-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edb57-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edb57-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edb57-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="edb57-112">See also</span></span>

- [<span data-ttu-id="edb57-113">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="edb57-113">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
