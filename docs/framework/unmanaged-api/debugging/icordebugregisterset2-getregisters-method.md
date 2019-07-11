---
title: Метод ICorDebugRegisterSet2::GetRegisters
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c1b90390689e709ee131935bd6417fa6b273eb2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769981"
---
# <a name="icordebugregisterset2getregisters-method"></a><span data-ttu-id="94d16-102">Метод ICorDebugRegisterSet2::GetRegisters</span><span class="sxs-lookup"><span data-stu-id="94d16-102">ICorDebugRegisterSet2::GetRegisters Method</span></span>
<span data-ttu-id="94d16-103">Получает значение каждого из регистров (для платформы, на котором в настоящее время выполняется код), указанный данной битовой маской.</span><span class="sxs-lookup"><span data-stu-id="94d16-103">Gets the value of each register (for the platform on which code is currently executing) that is specified by the given bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94d16-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94d16-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94d16-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="94d16-105">Parameters</span></span>  
 `maskCount`  
 <span data-ttu-id="94d16-106">[in] Размер в байтах из `mask` массива.</span><span class="sxs-lookup"><span data-stu-id="94d16-106">[in] The size, in bytes, of the `mask` array.</span></span>  
  
 `mask`  
 <span data-ttu-id="94d16-107">[in] Массив байтов, каждый бит соответствует регистру.</span><span class="sxs-lookup"><span data-stu-id="94d16-107">[in] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="94d16-108">Если бит равен 1, соответствующий регистр будет извлечено.</span><span class="sxs-lookup"><span data-stu-id="94d16-108">If the bit is 1, the corresponding register's value will be retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="94d16-109">[in] Количество значений регистров требуется получить.</span><span class="sxs-lookup"><span data-stu-id="94d16-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="94d16-110">[out] Массив `CORDB_REGISTER` объектов, каждый из которых получает значение регистра.</span><span class="sxs-lookup"><span data-stu-id="94d16-110">[out] An array of `CORDB_REGISTER` objects, each of which receives the value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94d16-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="94d16-111">Remarks</span></span>  
 <span data-ttu-id="94d16-112">`GetRegisters` Метод возвращает массив значений из регистров, которые определяются маски.</span><span class="sxs-lookup"><span data-stu-id="94d16-112">The `GetRegisters` method returns an array of values from the registers that are specified by the mask.</span></span> <span data-ttu-id="94d16-113">Массив не содержит значения, регистров, маска не задано.</span><span class="sxs-lookup"><span data-stu-id="94d16-113">The array does not contain values of registers whose mask bit is not set.</span></span> <span data-ttu-id="94d16-114">Таким образом, размер `regBuffer` массива должно быть равно количеству 1 в маске.</span><span class="sxs-lookup"><span data-stu-id="94d16-114">Thus, the size of the `regBuffer` array must be equal to the number of 1's in the mask.</span></span> <span data-ttu-id="94d16-115">Если значение `regCount` слишком мал для количество регистрами, указанными в маске, значения регистры с более будет усечен из набора.</span><span class="sxs-lookup"><span data-stu-id="94d16-115">If the value of `regCount` is too small for the number of registers indicated by the mask, the values of the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="94d16-116">Если `regCount` слишком велик, неиспользуемые `regBuffer` элементы будут изменены.</span><span class="sxs-lookup"><span data-stu-id="94d16-116">If `regCount` is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="94d16-117">Если маска указывает недоступный регистр, для этого регистра возвращается неопределенное значение.</span><span class="sxs-lookup"><span data-stu-id="94d16-117">If an unavailable register is indicated by the mask, an indeterminate value will be returned for that register.</span></span>  
  
 <span data-ttu-id="94d16-118">`ICorDebugRegisterSet2::GetRegisters` Метод необходим для платформ, которые имеют более 64 регистров.</span><span class="sxs-lookup"><span data-stu-id="94d16-118">The `ICorDebugRegisterSet2::GetRegisters` method is necessary for platforms which have more than 64 registers.</span></span> <span data-ttu-id="94d16-119">Например IA64 имеет 128 регистров общего назначения и 128 регистров с плавающей запятой, поэтому вам потребуется больше 64 бита в битовой маске.</span><span class="sxs-lookup"><span data-stu-id="94d16-119">For example, IA64 has 128 general purpose registers and 128 floating-point registers, so you need more than 64-bits in the bit mask.</span></span>  
  
 <span data-ttu-id="94d16-120">Если у вас более чем 64 регистры, как в случае на платформах, например x86, `GetRegisters` метод фактически переводит байты в `mask` массив байтов, в `ULONG64` , а затем вызывает [ICorDebugRegisterSet:: GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) метод, который принимает `ULONG64` маски.</span><span class="sxs-lookup"><span data-stu-id="94d16-120">If you do not have more than 64 registers, as is the case on platforms such as x86, the `GetRegisters` method actually just translates the bytes in the `mask` byte array into a `ULONG64` and then calls the [ICorDebugRegisterSet::GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) method, which takes the `ULONG64` mask.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94d16-121">Требования</span><span class="sxs-lookup"><span data-stu-id="94d16-121">Requirements</span></span>  
 <span data-ttu-id="94d16-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94d16-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94d16-123">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94d16-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94d16-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94d16-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94d16-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94d16-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94d16-126">См. также</span><span class="sxs-lookup"><span data-stu-id="94d16-126">See also</span></span>

- [<span data-ttu-id="94d16-127">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="94d16-127">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="94d16-128">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="94d16-128">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
