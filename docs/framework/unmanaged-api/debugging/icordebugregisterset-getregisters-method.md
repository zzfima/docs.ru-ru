---
title: Метод ICorDebugRegisterSet::GetRegisters
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: daee6c46c247bcd21073f779cada8c843947a949
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747246"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="46d76-102">Метод ICorDebugRegisterSet::GetRegisters</span><span class="sxs-lookup"><span data-stu-id="46d76-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="46d76-103">Получает значение каждого из регистров (на компьютере, на который в данный момент выполняется код), который указан битовой маской.</span><span class="sxs-lookup"><span data-stu-id="46d76-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46d76-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46d76-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46d76-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="46d76-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="46d76-106">[in] Битовую маску, которая указывает, зарегистрируйтесь, какие значения должны быть получены.</span><span class="sxs-lookup"><span data-stu-id="46d76-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="46d76-107">Каждый бит соответствует регистру.</span><span class="sxs-lookup"><span data-stu-id="46d76-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="46d76-108">Если немного присваивается одно, извлекается значение регистра; в противном случае значение регистра не извлекается.</span><span class="sxs-lookup"><span data-stu-id="46d76-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="46d76-109">[in] Количество значений регистров требуется получить.</span><span class="sxs-lookup"><span data-stu-id="46d76-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="46d76-110">[out] Массив `CORDB_REGISTER` объектов, каждый из которых получает значение регистра.</span><span class="sxs-lookup"><span data-stu-id="46d76-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46d76-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="46d76-111">Remarks</span></span>  
 <span data-ttu-id="46d76-112">Размер массива должно быть равно числу битов на один в битовой маске.</span><span class="sxs-lookup"><span data-stu-id="46d76-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="46d76-113">`regCount` Параметр указывает число элементов в буфер для получения значений регистров.</span><span class="sxs-lookup"><span data-stu-id="46d76-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="46d76-114">Если `regCount` значение слишком мал для числа регистрами, указанными в маске, регистры с более будет усечено из набора.</span><span class="sxs-lookup"><span data-stu-id="46d76-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="46d76-115">Если `regCount` значение слишком велико, неиспользуемые `regBuffer` элементы будут изменены.</span><span class="sxs-lookup"><span data-stu-id="46d76-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="46d76-116">Если битовая маска указывает регистр, который недоступен, `GetRegisters` возвращает неопределенное значение для этого регистра.</span><span class="sxs-lookup"><span data-stu-id="46d76-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46d76-117">Требования</span><span class="sxs-lookup"><span data-stu-id="46d76-117">Requirements</span></span>  
 <span data-ttu-id="46d76-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46d76-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46d76-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46d76-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46d76-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46d76-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46d76-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46d76-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d76-122">См. также</span><span class="sxs-lookup"><span data-stu-id="46d76-122">See also</span></span>

- [<span data-ttu-id="46d76-123">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="46d76-123">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="46d76-124">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="46d76-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
