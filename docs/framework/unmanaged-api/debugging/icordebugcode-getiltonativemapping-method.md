---
title: Метод ICorDebugCode::GetILToNativeMapping
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetILToNativeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 949cf322be4b7981a8c569f24abd1d9e29fa5ae6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973149"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="571c7-102">Метод ICorDebugCode::GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="571c7-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="571c7-103">Возвращает массив экземпляров «COR_DEBUG_IL_TO_NATIVE_MAP», которые представляют сопоставление из смещений промежуточного языка MSIL в собственные смещения.</span><span class="sxs-lookup"><span data-stu-id="571c7-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="571c7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="571c7-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="571c7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="571c7-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="571c7-106">[in] Размер массива `map`.</span><span class="sxs-lookup"><span data-stu-id="571c7-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="571c7-107">[out] Указатель на фактическое число элементов, возвращаемых в `map` массива.</span><span class="sxs-lookup"><span data-stu-id="571c7-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="571c7-108">[out] Массив `COR_DEBUG_IL_TO_NATIVE_MAP` структуры, каждый из которых представляет сопоставление смещение MSIL для смещения машинного кода.</span><span class="sxs-lookup"><span data-stu-id="571c7-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="571c7-109">Нет, не упорядочение массива возвращаемых элементов.</span><span class="sxs-lookup"><span data-stu-id="571c7-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="571c7-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="571c7-110">Remarks</span></span>  
 <span data-ttu-id="571c7-111">`GetILToNativeMapping` Метод возвращает значимые результаты только в том случае, если этот экземпляр «ICorDebugCode» представляет машинный код, который был just-in-time (JIT) скомпилированной на основе кода MSIL.</span><span class="sxs-lookup"><span data-stu-id="571c7-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="571c7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="571c7-112">Requirements</span></span>  
 <span data-ttu-id="571c7-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="571c7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="571c7-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="571c7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="571c7-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="571c7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="571c7-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="571c7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="571c7-117">См. также</span><span class="sxs-lookup"><span data-stu-id="571c7-117">See also</span></span>
- [<span data-ttu-id="571c7-118">Интерфейс ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="571c7-118">ICorDebugCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
