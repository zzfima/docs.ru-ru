---
title: "Метод ICorDebugRegisterSet::GetRegisters"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.GetRegisters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7edae3d3be1bcfb80b7a1e432fd5f25e119f078f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="cbec7-102">Метод ICorDebugRegisterSet::GetRegisters</span><span class="sxs-lookup"><span data-stu-id="cbec7-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="cbec7-103">Получает значение каждого регистра (на компьютере, который в данный момент выполняется код), который указан битовой маской.</span><span class="sxs-lookup"><span data-stu-id="cbec7-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbec7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbec7-104">Syntax</span></span>  
  
```  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cbec7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cbec7-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="cbec7-106">[in] Битовая маска, указывающая регистра, какие значения должны быть получены.</span><span class="sxs-lookup"><span data-stu-id="cbec7-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="cbec7-107">Каждый бит соответствует регистру.</span><span class="sxs-lookup"><span data-stu-id="cbec7-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="cbec7-108">Если бит присваивается одно, извлекается значение регистра; в противном случае — значение регистра не извлекается.</span><span class="sxs-lookup"><span data-stu-id="cbec7-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="cbec7-109">[in] Количество значений регистра требуется получить.</span><span class="sxs-lookup"><span data-stu-id="cbec7-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="cbec7-110">[out] Массив `CORDB_REGISTER` объектов, каждый из которых получает значение регистра.</span><span class="sxs-lookup"><span data-stu-id="cbec7-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbec7-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="cbec7-111">Remarks</span></span>  
 <span data-ttu-id="cbec7-112">Размер массива должно быть равно числу битов, значение в битовой маске.</span><span class="sxs-lookup"><span data-stu-id="cbec7-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="cbec7-113">`regCount` Указывает количество элементов в буфере, которые будут получать значения регистра.</span><span class="sxs-lookup"><span data-stu-id="cbec7-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="cbec7-114">Если `regCount` значение слишком мало для количества регистров, указанного маской, регистры с более будут отброшены из набора.</span><span class="sxs-lookup"><span data-stu-id="cbec7-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="cbec7-115">Если `regCount` значение слишком велико, неиспользуемые `regBuffer` элементы будут изменены.</span><span class="sxs-lookup"><span data-stu-id="cbec7-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="cbec7-116">Если битовая маска указывает недоступный регистр, `GetRegisters` возвращает неопределенное значение для данного регистра.</span><span class="sxs-lookup"><span data-stu-id="cbec7-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbec7-117">Требования</span><span class="sxs-lookup"><span data-stu-id="cbec7-117">Requirements</span></span>  
 <span data-ttu-id="cbec7-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbec7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbec7-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbec7-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbec7-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbec7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbec7-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbec7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbec7-122">См. также</span><span class="sxs-lookup"><span data-stu-id="cbec7-122">See Also</span></span>  
 [<span data-ttu-id="cbec7-123">ICorDebugRegisterSet-интерфейс</span><span class="sxs-lookup"><span data-stu-id="cbec7-123">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="cbec7-124">ICorDebugRegisterSet2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="cbec7-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
