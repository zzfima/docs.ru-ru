---
title: "Метод ICorDebugProcess::ReadMemory"
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
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2d282e83fc7b7632bde850ac1341eef938d8e0dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="2ec0c-102">Метод ICorDebugProcess::ReadMemory</span><span class="sxs-lookup"><span data-stu-id="2ec0c-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="2ec0c-103">Считывает заданную область памяти для этого процесса.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ec0c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ec0c-104">Syntax</span></span>  
  
```  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ec0c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ec0c-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="2ec0c-106">[in] Объект `CORDB_ADDRESS` значение, указывающее базовый адрес в памяти для чтения.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="2ec0c-107">[in] Число байтов, считываемых из памяти.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="2ec0c-108">[out] Буфер, получающий содержимое памяти.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="2ec0c-109">[out] Указатель на число байтов, переданных в указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ec0c-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ec0c-110">Remarks</span></span>  
 <span data-ttu-id="2ec0c-111">`ReadMemory` Метод в основном предназначен для использования при отладке взаимодействия для проверки областей памяти, используемых неуправляемой частью отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="2ec0c-112">Этот метод может также использоваться для чтения код на промежуточном языке (MSIL) и собственного JIT-скомпилированный код.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="2ec0c-113">Будут удалены все точки останова управляемого кода из данных, возвращаемых в `buffer` параметра.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="2ec0c-114">Каких-либо корректировок станет собственного точек останова, установленных [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="2ec0c-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="2ec0c-115">Кэширование памяти процесса не выполняется.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ec0c-116">Требования</span><span class="sxs-lookup"><span data-stu-id="2ec0c-116">Requirements</span></span>  
 <span data-ttu-id="2ec0c-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ec0c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ec0c-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ec0c-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ec0c-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ec0c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ec0c-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ec0c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
