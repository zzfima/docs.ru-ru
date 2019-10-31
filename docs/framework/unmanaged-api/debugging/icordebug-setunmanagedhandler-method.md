---
title: Метод ICorDebug::SetUnmanagedHandler
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
ms.openlocfilehash: 36d314211d95dff6648753f5d550a2cfd402a918
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134050"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="32b30-102">Метод ICorDebug::SetUnmanagedHandler</span><span class="sxs-lookup"><span data-stu-id="32b30-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="32b30-103">Указывает объект обработчика событий для неуправляемых событий.</span><span class="sxs-lookup"><span data-stu-id="32b30-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32b30-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32b30-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32b30-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="32b30-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="32b30-106">окне Указатель на объект [икордебугунманажедкаллбакк](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) , представляющий обработчик событий для неуправляемых событий.</span><span class="sxs-lookup"><span data-stu-id="32b30-106">[in] A pointer to an [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32b30-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="32b30-107">Remarks</span></span>  
 <span data-ttu-id="32b30-108">Объект обработчика событий для неуправляемых событий должен быть задан после вызова метода [ICorDebug:: Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) и перед вызовом [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) или [ICorDebug::D ебугактивепроцесс](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span><span class="sxs-lookup"><span data-stu-id="32b30-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="32b30-109">Однако для устаревших целей не требуется задавать объект обработчика событий для неуправляемых событий до тех пор, пока не будет вызвано первое собственное событие отладки.</span><span class="sxs-lookup"><span data-stu-id="32b30-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="32b30-110">В частности, если `ICorDebug::CreateProcess` установлен флаг CREATE_SUSPENDED, события отладки машинного кода не могут быть отправлены, пока основной поток не возобновит работу.</span><span class="sxs-lookup"><span data-stu-id="32b30-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32b30-111">Требования</span><span class="sxs-lookup"><span data-stu-id="32b30-111">Requirements</span></span>  
 <span data-ttu-id="32b30-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32b30-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32b30-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32b30-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32b30-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32b30-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32b30-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32b30-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32b30-116">См. также</span><span class="sxs-lookup"><span data-stu-id="32b30-116">See also</span></span>

- [<span data-ttu-id="32b30-117">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="32b30-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
