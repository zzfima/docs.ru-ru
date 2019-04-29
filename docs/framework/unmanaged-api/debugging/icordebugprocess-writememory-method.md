---
title: Метод ICorDebugProcess::WriteMemory
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e9d640fb1c9dae5bb195baa504e560ba8e45821
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930303"
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="8d6f3-102">Метод ICorDebugProcess::WriteMemory</span><span class="sxs-lookup"><span data-stu-id="8d6f3-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="8d6f3-103">Записывает данные в область памяти, в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="8d6f3-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d6f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d6f3-104">Syntax</span></span>  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d6f3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8d6f3-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="8d6f3-106">[in] Объект `CORDB_ADDRESS` записывается значение, базовый адрес области памяти для данных.</span><span class="sxs-lookup"><span data-stu-id="8d6f3-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="8d6f3-107">Прежде чем происходит передача данных, система проверяет, область памяти указанного размера, начиная с базового адреса, доступного для записи.</span><span class="sxs-lookup"><span data-stu-id="8d6f3-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="8d6f3-108">Если он недоступен, происходит сбой метода.</span><span class="sxs-lookup"><span data-stu-id="8d6f3-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="8d6f3-109">[in] Число байтов для записи в область памяти.</span><span class="sxs-lookup"><span data-stu-id="8d6f3-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="8d6f3-110">[in] Буфер, содержащий записываемые данные.</span><span class="sxs-lookup"><span data-stu-id="8d6f3-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="8d6f3-111">[out] Указатель на переменную, которая получает число байтов, записанных в область памяти, в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="8d6f3-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="8d6f3-112">Если `written` имеет значение NULL, этот параметр учитывается.</span><span class="sxs-lookup"><span data-stu-id="8d6f3-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d6f3-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d6f3-113">Remarks</span></span>  
 <span data-ttu-id="8d6f3-114">Данные автоматически записываются за любыми точками останова.</span><span class="sxs-lookup"><span data-stu-id="8d6f3-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="8d6f3-115">В платформе .NET Framework версии 2.0 машинные отладчики не следует использовать этот метод для вставки точки останова в потоке инструкций.</span><span class="sxs-lookup"><span data-stu-id="8d6f3-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="8d6f3-116">Используйте [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="8d6f3-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="8d6f3-117">`WriteMemory` Метод должен использоваться только за пределами управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="8d6f3-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="8d6f3-118">Этот метод может привести к повреждению среды выполнения при неправильном.</span><span class="sxs-lookup"><span data-stu-id="8d6f3-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d6f3-119">Требования</span><span class="sxs-lookup"><span data-stu-id="8d6f3-119">Requirements</span></span>  
 <span data-ttu-id="8d6f3-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d6f3-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d6f3-121">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d6f3-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d6f3-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d6f3-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d6f3-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d6f3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
