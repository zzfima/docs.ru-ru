---
title: "Метод ICorDebugRegisterSet2::GetRegistersAvailable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet2.GetRegistersAvailable
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f91b30b2ab50fc74049365d5c290bbaae1e20b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="267d4-102">Метод ICorDebugRegisterSet2::GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="267d4-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="267d4-103">Возвращает массив байтов, предоставляющий растровое изображение доступных регистров.</span><span class="sxs-lookup"><span data-stu-id="267d4-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="267d4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="267d4-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="267d4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="267d4-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="267d4-106">[in] Размер массива `availableRegChunks`.</span><span class="sxs-lookup"><span data-stu-id="267d4-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="267d4-107">[out] Массив байтов, из которых каждый бит соответствует регистру.</span><span class="sxs-lookup"><span data-stu-id="267d4-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="267d4-108">Если регистр, соответствующий бит регистра устанавливается.</span><span class="sxs-lookup"><span data-stu-id="267d4-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="267d4-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="267d4-109">Remarks</span></span>  
 <span data-ttu-id="267d4-110">Значения перечисления CorDebugRegister указывают регистры различных микропроцессоров.</span><span class="sxs-lookup"><span data-stu-id="267d4-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="267d4-111">Верхние пять бит каждое значение — это индекс в `availableRegChunks` массива байтов.</span><span class="sxs-lookup"><span data-stu-id="267d4-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="267d4-112">Три младших битов каждого значения идентифицируют положение бита в индексируемом байте.</span><span class="sxs-lookup"><span data-stu-id="267d4-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="267d4-113">Получает `CorDebugRegister` значение, которое указывает определенный регистр, положение регистра в маске определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="267d4-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1.  <span data-ttu-id="267d4-114">Извлеките индекс, необходимые для доступа к правильно байта в `availableRegChunks` массива:</span><span class="sxs-lookup"><span data-stu-id="267d4-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="267d4-115">`CorDebugRegister`Значение >> 3</span><span class="sxs-lookup"><span data-stu-id="267d4-115">`CorDebugRegister` value >> 3</span></span>  
  
2.  <span data-ttu-id="267d4-116">Извлеките позиция разряда в индексируемом байте, в котором нулевой бит является наименее значимым битом:</span><span class="sxs-lookup"><span data-stu-id="267d4-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="267d4-117">`CorDebugRegister`значение & 7</span><span class="sxs-lookup"><span data-stu-id="267d4-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="267d4-118">Требования</span><span class="sxs-lookup"><span data-stu-id="267d4-118">Requirements</span></span>  
 <span data-ttu-id="267d4-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="267d4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="267d4-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="267d4-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="267d4-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="267d4-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="267d4-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="267d4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="267d4-123">См. также</span><span class="sxs-lookup"><span data-stu-id="267d4-123">See Also</span></span>  
 [<span data-ttu-id="267d4-124">ICorDebugRegisterSet2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="267d4-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [<span data-ttu-id="267d4-125">ICorDebugRegisterSet-интерфейс</span><span class="sxs-lookup"><span data-stu-id="267d4-125">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
