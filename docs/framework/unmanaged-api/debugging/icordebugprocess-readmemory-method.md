---
title: Метод ICorDebugProcess::ReadMemory
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d74da502492065dbffb5e5499581263760636c7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737076"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="7d3f6-102">Метод ICorDebugProcess::ReadMemory</span><span class="sxs-lookup"><span data-stu-id="7d3f6-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="7d3f6-103">Считывает в указанную область памяти для этого процесса.</span><span class="sxs-lookup"><span data-stu-id="7d3f6-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d3f6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d3f6-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d3f6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d3f6-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="7d3f6-106">[in] Объект `CORDB_ADDRESS` значение, указывающее базовый адрес в памяти для чтения.</span><span class="sxs-lookup"><span data-stu-id="7d3f6-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="7d3f6-107">[in] Число байтов, считываемых из памяти.</span><span class="sxs-lookup"><span data-stu-id="7d3f6-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="7d3f6-108">[out] Буфер, получающий содержимое памяти.</span><span class="sxs-lookup"><span data-stu-id="7d3f6-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="7d3f6-109">[out] Указатель на число байтов, переданных в указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="7d3f6-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d3f6-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d3f6-110">Remarks</span></span>  
 <span data-ttu-id="7d3f6-111">`ReadMemory` Метод в основном предназначен для использования при отладке взаимодействия для проверки областей памяти, используются ли в неуправляемой части отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="7d3f6-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="7d3f6-112">Этот метод можно также прочитать код на промежуточном языке (MSIL) и собственного JIT-скомпилированный код.</span><span class="sxs-lookup"><span data-stu-id="7d3f6-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="7d3f6-113">Все управляемые точки останова будут удалены из данных, который возвращается в `buffer` параметра.</span><span class="sxs-lookup"><span data-stu-id="7d3f6-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="7d3f6-114">Каких-либо корректировок станет собственного точек останова, установленных [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="7d3f6-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="7d3f6-115">Кэширование памяти процесса не выполняется.</span><span class="sxs-lookup"><span data-stu-id="7d3f6-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d3f6-116">Требования</span><span class="sxs-lookup"><span data-stu-id="7d3f6-116">Requirements</span></span>  
 <span data-ttu-id="7d3f6-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d3f6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d3f6-118">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d3f6-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d3f6-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d3f6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d3f6-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d3f6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
