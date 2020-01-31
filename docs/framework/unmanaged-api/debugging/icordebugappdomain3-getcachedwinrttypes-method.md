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
ms.openlocfilehash: 55d0b40bbdb5628f60090d9d70f7dccbebe9d58f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784998"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="b41f9-102">Метод ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="b41f9-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="b41f9-103">Возвращает перечислитель для всех кэшированных среда выполнения Windowsных типов.</span><span class="sxs-lookup"><span data-stu-id="b41f9-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b41f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b41f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b41f9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b41f9-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="b41f9-106">заполняет Указатель на объект интерфейса [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md) , который может перечислить управляемые представления среда выполнения Windows типов, загруженных в домен приложения в данный момент.</span><span class="sxs-lookup"><span data-stu-id="b41f9-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b41f9-107">Требования</span><span class="sxs-lookup"><span data-stu-id="b41f9-107">Requirements</span></span>  
 <span data-ttu-id="b41f9-108">**Платформы:** среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="b41f9-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="b41f9-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b41f9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b41f9-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b41f9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b41f9-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b41f9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b41f9-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="b41f9-112">See also</span></span>

- [<span data-ttu-id="b41f9-113">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="b41f9-113">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
