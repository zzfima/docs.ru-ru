---
title: Метод ICorDebugChain::EnumerateFrames
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7568f8ca3b92ef465ab595348f68895f389d61e4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489713"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="a199d-102">Метод ICorDebugChain::EnumerateFrames</span><span class="sxs-lookup"><span data-stu-id="a199d-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="a199d-103">Возвращает перечислитель, содержащий все управляемые фреймы стека в цепочке, начиная с последнего.</span><span class="sxs-lookup"><span data-stu-id="a199d-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a199d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a199d-104">Syntax</span></span>  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a199d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a199d-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="a199d-106">[out] Указатель на адрес объекта ICorDebugFrameEnum, который является перечислителем для кадров стека.</span><span class="sxs-lookup"><span data-stu-id="a199d-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a199d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a199d-107">Remarks</span></span>  
 <span data-ttu-id="a199d-108">Цепь представляет физический стек вызова для потока.</span><span class="sxs-lookup"><span data-stu-id="a199d-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="a199d-109">`EnumerateFrames` Метод должен вызываться только для управляемых цепочек.</span><span class="sxs-lookup"><span data-stu-id="a199d-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="a199d-110">API отладки не поддерживает методы для получения кадров, содержащихся в неуправляемых цепочки.</span><span class="sxs-lookup"><span data-stu-id="a199d-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="a199d-111">Отладчик должен использовать другие средства для получения этих сведений.</span><span class="sxs-lookup"><span data-stu-id="a199d-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a199d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="a199d-112">Requirements</span></span>  
 <span data-ttu-id="a199d-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a199d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a199d-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a199d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a199d-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a199d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a199d-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a199d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
