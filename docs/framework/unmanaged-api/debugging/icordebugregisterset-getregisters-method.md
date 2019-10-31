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
ms.openlocfilehash: 112d530c765fc74ab4ea767cb3168977d1b45f47
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138363"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="a80ee-102">Метод ICorDebugRegisterSet::GetRegisters</span><span class="sxs-lookup"><span data-stu-id="a80ee-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="a80ee-103">Возвращает значение каждого регистра (на компьютере, выполняющем в данный момент код), который задается битовой маской.</span><span class="sxs-lookup"><span data-stu-id="a80ee-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a80ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a80ee-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a80ee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a80ee-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="a80ee-106">окне Битовая маска, указывающая, какие значения регистров должны быть извлечены.</span><span class="sxs-lookup"><span data-stu-id="a80ee-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="a80ee-107">Каждый бит соответствует регистру.</span><span class="sxs-lookup"><span data-stu-id="a80ee-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="a80ee-108">Если бит задан равным 1, то значение регистра извлекается; в противном случае значение регистра не извлекается.</span><span class="sxs-lookup"><span data-stu-id="a80ee-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="a80ee-109">окне Число возвращаемых значений регистров.</span><span class="sxs-lookup"><span data-stu-id="a80ee-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="a80ee-110">заполняет Массив объектов `CORDB_REGISTER`, каждый из которых получает значение регистра.</span><span class="sxs-lookup"><span data-stu-id="a80ee-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a80ee-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="a80ee-111">Remarks</span></span>  
 <span data-ttu-id="a80ee-112">Размер массива должен быть равен числу битов, равным одному в битовой маске.</span><span class="sxs-lookup"><span data-stu-id="a80ee-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="a80ee-113">Параметр `regCount` задает количество элементов в буфере, которые будут принимать значения регистров.</span><span class="sxs-lookup"><span data-stu-id="a80ee-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="a80ee-114">Если значение `regCount` слишком мало для количества регистров, указанных маской, то более высокие числовые регистры будут обрезаны из набора.</span><span class="sxs-lookup"><span data-stu-id="a80ee-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="a80ee-115">Если значение `regCount` слишком велико, неиспользуемые элементы `regBuffer` будут неизменными.</span><span class="sxs-lookup"><span data-stu-id="a80ee-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="a80ee-116">Если битовая маска указывает недоступный регистр, `GetRegisters` возвращает неопределенное значение для этого регистра.</span><span class="sxs-lookup"><span data-stu-id="a80ee-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a80ee-117">Требования</span><span class="sxs-lookup"><span data-stu-id="a80ee-117">Requirements</span></span>  
 <span data-ttu-id="a80ee-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a80ee-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a80ee-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a80ee-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a80ee-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a80ee-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a80ee-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a80ee-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a80ee-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a80ee-122">See also</span></span>

- [<span data-ttu-id="a80ee-123">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="a80ee-123">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="a80ee-124">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="a80ee-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
