---
title: "Метод ICorDebugProcess::WriteMemory"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugProcess.WriteMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2a1a12d1393d1db69ea47833958fdf828b552064
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="8f697-102">Метод ICorDebugProcess::WriteMemory</span><span class="sxs-lookup"><span data-stu-id="8f697-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="8f697-103">Записывает данные в область памяти в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="8f697-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f697-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f697-104">Syntax</span></span>  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f697-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8f697-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="8f697-106">[in] Объект `CORDB_ADDRESS` записывается значение, базовый адрес области памяти для данных.</span><span class="sxs-lookup"><span data-stu-id="8f697-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="8f697-107">Прежде чем произойдет передача данных, система проверяет, область памяти указанного размера, начиная с базового адреса, доступен для записи.</span><span class="sxs-lookup"><span data-stu-id="8f697-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="8f697-108">Если он недоступен, произойдет ошибка.</span><span class="sxs-lookup"><span data-stu-id="8f697-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="8f697-109">[in] Число байтов для записи в область памяти.</span><span class="sxs-lookup"><span data-stu-id="8f697-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="8f697-110">[in] Буфер, содержащий записываемые данные.</span><span class="sxs-lookup"><span data-stu-id="8f697-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="8f697-111">[out] Указатель на переменную, которая получает число байтов, записанных в область памяти, в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="8f697-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="8f697-112">Если `written` имеет значение NULL, этот параметр учитывается.</span><span class="sxs-lookup"><span data-stu-id="8f697-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f697-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="8f697-113">Remarks</span></span>  
 <span data-ttu-id="8f697-114">Данные автоматически записываются за любыми точками останова.</span><span class="sxs-lookup"><span data-stu-id="8f697-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="8f697-115">В платформе .NET Framework версии 2.0 машинные отладчики не следует использовать этот метод для вставки точки останова в поток инструкций.</span><span class="sxs-lookup"><span data-stu-id="8f697-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="8f697-116">Используйте [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) вместо него.</span><span class="sxs-lookup"><span data-stu-id="8f697-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="8f697-117">`WriteMemory` Метод должен использоваться только за пределами управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="8f697-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="8f697-118">Этот метод может привести к повреждению среды выполнения при неправильном.</span><span class="sxs-lookup"><span data-stu-id="8f697-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f697-119">Требования</span><span class="sxs-lookup"><span data-stu-id="8f697-119">Requirements</span></span>  
 <span data-ttu-id="8f697-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f697-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f697-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f697-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f697-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f697-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f697-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f697-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
