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
ms.openlocfilehash: 0b024d3396dfe1796fcb18afa122d4aee39c4ccc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132724"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="c127b-102">Метод ICorDebugChain::EnumerateFrames</span><span class="sxs-lookup"><span data-stu-id="c127b-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="c127b-103">Возвращает перечислитель, содержащий все управляемые кадры стека в цепочке, начиная с самого последнего кадра.</span><span class="sxs-lookup"><span data-stu-id="c127b-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c127b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c127b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c127b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c127b-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="c127b-106">заполняет Указатель на адрес объекта ICorDebugFrameEnum, который является перечислителем для кадров стека.</span><span class="sxs-lookup"><span data-stu-id="c127b-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c127b-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="c127b-107">Remarks</span></span>  
 <span data-ttu-id="c127b-108">Цепочка представляет физический стек вызовов для потока.</span><span class="sxs-lookup"><span data-stu-id="c127b-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="c127b-109">Метод `EnumerateFrames` должен вызываться только для управляемых цепочек.</span><span class="sxs-lookup"><span data-stu-id="c127b-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="c127b-110">API отладки не предоставляет методы для получения кадров, содержащихся в неуправляемых цепочках.</span><span class="sxs-lookup"><span data-stu-id="c127b-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="c127b-111">Для получения этих сведений отладчик должен использовать другие средства.</span><span class="sxs-lookup"><span data-stu-id="c127b-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c127b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c127b-112">Requirements</span></span>  
 <span data-ttu-id="c127b-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c127b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c127b-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c127b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c127b-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c127b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c127b-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c127b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
