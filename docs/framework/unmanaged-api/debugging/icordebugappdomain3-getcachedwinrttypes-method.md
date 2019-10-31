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
ms.openlocfilehash: 89f45208550d49f214e763728ddc9eb1bfcd9800
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088972"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="01b90-102">Метод ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="01b90-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="01b90-103">Возвращает перечислитель для всех кэшированных среда выполнения Windowsных типов.</span><span class="sxs-lookup"><span data-stu-id="01b90-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01b90-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01b90-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="01b90-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="01b90-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="01b90-106">заполняет Указатель на объект интерфейса [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) , который может перечислить управляемые представления среда выполнения Windows типов, загруженных в домен приложения в данный момент.</span><span class="sxs-lookup"><span data-stu-id="01b90-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01b90-107">Требования</span><span class="sxs-lookup"><span data-stu-id="01b90-107">Requirements</span></span>  
 <span data-ttu-id="01b90-108">**Платформы:** среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="01b90-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="01b90-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01b90-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01b90-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01b90-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01b90-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01b90-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01b90-112">См. также</span><span class="sxs-lookup"><span data-stu-id="01b90-112">See also</span></span>

- [<span data-ttu-id="01b90-113">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="01b90-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
