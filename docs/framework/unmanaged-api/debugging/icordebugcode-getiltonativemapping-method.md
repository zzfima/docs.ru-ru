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
ms.openlocfilehash: 98709c0ce7469db1d0365d71e10d2d021cd3b3f0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777888"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="e916d-102">Метод ICorDebugCode::GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="e916d-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="e916d-103">Возвращает массив экземпляров "COR_DEBUG_IL_TO_NATIVE_MAP", которые представляют сопоставления из смещений MSIL к собственным смещениям.</span><span class="sxs-lookup"><span data-stu-id="e916d-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e916d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e916d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e916d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e916d-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="e916d-106">[in] Размер массива `map`.</span><span class="sxs-lookup"><span data-stu-id="e916d-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="e916d-107">заполняет Указатель на фактическое число элементов, возвращаемых в массиве `map`.</span><span class="sxs-lookup"><span data-stu-id="e916d-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="e916d-108">заполняет Массив структур `COR_DEBUG_IL_TO_NATIVE_MAP`, каждый из которых представляет сопоставление смещения MSIL со смещением в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="e916d-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="e916d-109">Порядок для массива возвращаемых элементов отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e916d-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e916d-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="e916d-110">Remarks</span></span>  
 <span data-ttu-id="e916d-111">Метод `GetILToNativeMapping` возвращает значимые результаты только в том случае, если этот экземпляр "ICorDebugCode" представляет машинный код, который был JIT-скомпилирован из кода MSIL.</span><span class="sxs-lookup"><span data-stu-id="e916d-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e916d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e916d-112">Requirements</span></span>  
 <span data-ttu-id="e916d-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e916d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e916d-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e916d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e916d-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e916d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e916d-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e916d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e916d-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="e916d-117">See also</span></span>

- [<span data-ttu-id="e916d-118">Интерфейс ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="e916d-118">ICorDebugCode Interface</span></span>](icordebugcode-interface1.md)
