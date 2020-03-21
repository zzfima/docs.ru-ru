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
ms.openlocfilehash: 32e899622b9c649a08e3bca1b6645f70dcbcbb19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178545"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="b7ef3-102">Метод ICorDebugRegisterSet::GetRegisters</span><span class="sxs-lookup"><span data-stu-id="b7ef3-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="b7ef3-103">Получает значение каждого регистра (на компьютере, который в настоящее время является исполнителем кода), которое указывается битной маской.</span><span class="sxs-lookup"><span data-stu-id="b7ef3-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7ef3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7ef3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7ef3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b7ef3-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="b7ef3-106">(в) Битная маска, которая определяет, какие значения регистра должны быть извлечены.</span><span class="sxs-lookup"><span data-stu-id="b7ef3-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="b7ef3-107">Каждый бит соответствует регистру.</span><span class="sxs-lookup"><span data-stu-id="b7ef3-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="b7ef3-108">Если немного настроено на один, значение регистра извлекается; в противном случае значение регистра не извлекается.</span><span class="sxs-lookup"><span data-stu-id="b7ef3-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="b7ef3-109">(в) Количество значений регистра, которые необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="b7ef3-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="b7ef3-110">(ваут) Массив объектов, `CORDB_REGISTER` каждый из которых получает значение регистра.</span><span class="sxs-lookup"><span data-stu-id="b7ef3-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7ef3-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="b7ef3-111">Remarks</span></span>  
 <span data-ttu-id="b7ef3-112">Размер массива должен быть равен количеству битов, установленных на один в битной маске.</span><span class="sxs-lookup"><span data-stu-id="b7ef3-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="b7ef3-113">Параметр `regCount` определяет количество элементов в буфере, которые будут получать значения регистра.</span><span class="sxs-lookup"><span data-stu-id="b7ef3-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="b7ef3-114">Если `regCount` значение слишком мало для числа регистров, указанных в маске, более высокие пронумерованные регистры будут усечены из набора.</span><span class="sxs-lookup"><span data-stu-id="b7ef3-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="b7ef3-115">Если `regCount` значение слишком велико, `regBuffer` неиспользованные элементы будут неизменены.</span><span class="sxs-lookup"><span data-stu-id="b7ef3-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="b7ef3-116">Если битовая маска определяет регистр, который `GetRegisters` недоступен, возвращает неопределенное значение для этого регистра.</span><span class="sxs-lookup"><span data-stu-id="b7ef3-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7ef3-117">Требования</span><span class="sxs-lookup"><span data-stu-id="b7ef3-117">Requirements</span></span>  
 <span data-ttu-id="b7ef3-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7ef3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7ef3-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7ef3-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7ef3-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7ef3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7ef3-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7ef3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7ef3-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b7ef3-122">See also</span></span>

- [<span data-ttu-id="b7ef3-123">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="b7ef3-123">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="b7ef3-124">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="b7ef3-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
