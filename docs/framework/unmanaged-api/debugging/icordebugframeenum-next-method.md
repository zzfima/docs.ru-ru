---
title: Метод ICorDebugFrameEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68098895b2ad7f5c08d30f222777e52d4ee3f063
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995804"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="b40ce-102">Метод ICorDebugFrameEnum::Next</span><span class="sxs-lookup"><span data-stu-id="b40ce-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="b40ce-103">Возвращает заданное число экземпляров ICorDebugFrame, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="b40ce-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b40ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b40ce-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b40ce-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b40ce-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b40ce-106">[in] Количество `ICorDebugFrame` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b40ce-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="b40ce-107">[out] Массив указателей, каждый из которых указывает `ICorDebugFrame` объекта.</span><span class="sxs-lookup"><span data-stu-id="b40ce-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b40ce-108">[out] Указатель на число `ICorDebugFrame` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b40ce-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="b40ce-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="b40ce-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b40ce-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b40ce-110">Requirements</span></span>  
 <span data-ttu-id="b40ce-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b40ce-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b40ce-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b40ce-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b40ce-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b40ce-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b40ce-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b40ce-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
