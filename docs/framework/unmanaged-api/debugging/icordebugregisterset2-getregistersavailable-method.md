---
title: Метод ICorDebugRegisterSet2::GetRegistersAvailable
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 071c9c9cbdb47372903ef418a4f21450d8071f8c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614069"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="548b6-102">Метод ICorDebugRegisterSet2::GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="548b6-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="548b6-103">Возвращает массив байтов, предоставляет битовую схему, доступных регистров.</span><span class="sxs-lookup"><span data-stu-id="548b6-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="548b6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="548b6-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="548b6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="548b6-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="548b6-106">[in] Размер массива `availableRegChunks`.</span><span class="sxs-lookup"><span data-stu-id="548b6-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="548b6-107">[out] Массив байтов, каждый бит соответствует регистру.</span><span class="sxs-lookup"><span data-stu-id="548b6-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="548b6-108">Если регистр, устанавливается соответствующий бит в регистре.</span><span class="sxs-lookup"><span data-stu-id="548b6-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="548b6-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="548b6-109">Remarks</span></span>  
 <span data-ttu-id="548b6-110">Значения перечисления CorDebugRegister указывают регистры различных микропроцессоров.</span><span class="sxs-lookup"><span data-stu-id="548b6-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="548b6-111">Старшие разряды пять каждому значению типа являются порядковым номером в `availableRegChunks` массив байтов.</span><span class="sxs-lookup"><span data-stu-id="548b6-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="548b6-112">Нижние три бит каждого значения идентифицируют положение бита в индексируемом байте.</span><span class="sxs-lookup"><span data-stu-id="548b6-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="548b6-113">Учитывая `CorDebugRegister` значение, указывающее определенный регистр, положение регистра в маске определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="548b6-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1.  <span data-ttu-id="548b6-114">Извлечь индекс, необходимые для доступа к правильный байта в `availableRegChunks` массива:</span><span class="sxs-lookup"><span data-stu-id="548b6-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="548b6-115">`CorDebugRegister` Значение >> 3</span><span class="sxs-lookup"><span data-stu-id="548b6-115">`CorDebugRegister` value >> 3</span></span>  
  
2.  <span data-ttu-id="548b6-116">Извлеките положение бита в индексированных байт, где нулевой бит — наименее значимым битом.</span><span class="sxs-lookup"><span data-stu-id="548b6-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="548b6-117">`CorDebugRegister` значение & 7</span><span class="sxs-lookup"><span data-stu-id="548b6-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="548b6-118">Требования</span><span class="sxs-lookup"><span data-stu-id="548b6-118">Requirements</span></span>  
 <span data-ttu-id="548b6-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="548b6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="548b6-120">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="548b6-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="548b6-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="548b6-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="548b6-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="548b6-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="548b6-123">См. также</span><span class="sxs-lookup"><span data-stu-id="548b6-123">See also</span></span>
- [<span data-ttu-id="548b6-124">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="548b6-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="548b6-125">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="548b6-125">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
