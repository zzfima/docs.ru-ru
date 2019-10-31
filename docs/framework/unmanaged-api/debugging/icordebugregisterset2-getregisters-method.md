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
ms.openlocfilehash: 8e5583acfe338c185200c0b8e41b7d6e051fa146
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131356"
---
# <a name="icordebugregisterset2getregisters-method"></a><span data-ttu-id="ca78c-102">Метод ICorDebugRegisterSet2::GetRegisters</span><span class="sxs-lookup"><span data-stu-id="ca78c-102">ICorDebugRegisterSet2::GetRegisters Method</span></span>
<span data-ttu-id="ca78c-103">Возвращает значение каждого регистра (для платформы, в которой код выполняется в данный момент), заданный заданной битовой маской.</span><span class="sxs-lookup"><span data-stu-id="ca78c-103">Gets the value of each register (for the platform on which code is currently executing) that is specified by the given bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca78c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca78c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca78c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca78c-105">Parameters</span></span>  
 `maskCount`  
 <span data-ttu-id="ca78c-106">окне Размер массива `mask` в байтах.</span><span class="sxs-lookup"><span data-stu-id="ca78c-106">[in] The size, in bytes, of the `mask` array.</span></span>  
  
 `mask`  
 <span data-ttu-id="ca78c-107">окне Массив байтов, каждый бит которого соответствует регистру.</span><span class="sxs-lookup"><span data-stu-id="ca78c-107">[in] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="ca78c-108">Если бит равен 1, будет получено соответствующее значение регистра.</span><span class="sxs-lookup"><span data-stu-id="ca78c-108">If the bit is 1, the corresponding register's value will be retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="ca78c-109">окне Число возвращаемых значений регистров.</span><span class="sxs-lookup"><span data-stu-id="ca78c-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="ca78c-110">заполняет Массив объектов `CORDB_REGISTER`, каждый из которых получает значение регистра.</span><span class="sxs-lookup"><span data-stu-id="ca78c-110">[out] An array of `CORDB_REGISTER` objects, each of which receives the value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca78c-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="ca78c-111">Remarks</span></span>  
 <span data-ttu-id="ca78c-112">Метод `GetRegisters` возвращает массив значений из регистров, заданных маской.</span><span class="sxs-lookup"><span data-stu-id="ca78c-112">The `GetRegisters` method returns an array of values from the registers that are specified by the mask.</span></span> <span data-ttu-id="ca78c-113">Массив не содержит значений регистров, бит маски которых не задан.</span><span class="sxs-lookup"><span data-stu-id="ca78c-113">The array does not contain values of registers whose mask bit is not set.</span></span> <span data-ttu-id="ca78c-114">Таким же размером массив `regBuffer` должен быть равен количеству 1 в маске.</span><span class="sxs-lookup"><span data-stu-id="ca78c-114">Thus, the size of the `regBuffer` array must be equal to the number of 1's in the mask.</span></span> <span data-ttu-id="ca78c-115">Если значение `regCount` слишком мало для количества регистров, указанных маской, значения более высоких регистров будут обрезаны из набора.</span><span class="sxs-lookup"><span data-stu-id="ca78c-115">If the value of `regCount` is too small for the number of registers indicated by the mask, the values of the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="ca78c-116">Если `regCount` слишком большой, неиспользуемые элементы `regBuffer` будут неизменными.</span><span class="sxs-lookup"><span data-stu-id="ca78c-116">If `regCount` is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="ca78c-117">Если недоступная ККМ обозначается маской, для этой регистрации будет возвращено неопределенное значение.</span><span class="sxs-lookup"><span data-stu-id="ca78c-117">If an unavailable register is indicated by the mask, an indeterminate value will be returned for that register.</span></span>  
  
 <span data-ttu-id="ca78c-118">Метод `ICorDebugRegisterSet2::GetRegisters` необходим для платформ, имеющих более 64 регистров.</span><span class="sxs-lookup"><span data-stu-id="ca78c-118">The `ICorDebugRegisterSet2::GetRegisters` method is necessary for platforms which have more than 64 registers.</span></span> <span data-ttu-id="ca78c-119">Например, IA64 имеет 128 регистров общего назначения и 128 регистров с плавающей запятой, поэтому в битовой маске требуется более 64 бит.</span><span class="sxs-lookup"><span data-stu-id="ca78c-119">For example, IA64 has 128 general purpose registers and 128 floating-point registers, so you need more than 64-bits in the bit mask.</span></span>  
  
 <span data-ttu-id="ca78c-120">Если у вас больше 64 регистров, как в случае с платформами, такими как x86, то метод `GetRegisters` фактически преобразует байты в `mask` массиве байтов в `ULONG64`, а затем вызывает метод [ICorDebugRegisterSet:: GetBytes.](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) , который принимает маску `ULONG64`.</span><span class="sxs-lookup"><span data-stu-id="ca78c-120">If you do not have more than 64 registers, as is the case on platforms such as x86, the `GetRegisters` method actually just translates the bytes in the `mask` byte array into a `ULONG64` and then calls the [ICorDebugRegisterSet::GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) method, which takes the `ULONG64` mask.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca78c-121">Требования</span><span class="sxs-lookup"><span data-stu-id="ca78c-121">Requirements</span></span>  
 <span data-ttu-id="ca78c-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca78c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca78c-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca78c-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca78c-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca78c-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca78c-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca78c-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca78c-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ca78c-126">See also</span></span>

- [<span data-ttu-id="ca78c-127">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="ca78c-127">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="ca78c-128">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="ca78c-128">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
