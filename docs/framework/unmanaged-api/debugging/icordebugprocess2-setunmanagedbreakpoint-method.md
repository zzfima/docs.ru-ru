---
title: Метод ICorDebugProcess2::SetUnmanagedBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type:
- apiref
ms.openlocfilehash: fb8b8f3e29c141e91587a4d0cdc81cdabccdbc9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178649"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="b6f9a-102">Метод ICorDebugProcess2::SetUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="b6f9a-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="b6f9a-103">Устанавливает неуправляемую точку разрыва в указанном смещении родного изображения.</span><span class="sxs-lookup"><span data-stu-id="b6f9a-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6f9a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6f9a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6f9a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b6f9a-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="b6f9a-106">(в) Объект, `CORDB_ADDRESS` опознававательный смещение родного изображения.</span><span class="sxs-lookup"><span data-stu-id="b6f9a-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="b6f9a-107">(в) Размер массива, `buffer` в байтах.</span><span class="sxs-lookup"><span data-stu-id="b6f9a-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="b6f9a-108">(ваут) Массив, содержащий opcode, который заменяется точкой разрыва.</span><span class="sxs-lookup"><span data-stu-id="b6f9a-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="b6f9a-109">(ваут) Указатель на количество байтов, `buffer` возвращенных в массиве.</span><span class="sxs-lookup"><span data-stu-id="b6f9a-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6f9a-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b6f9a-110">Remarks</span></span>  
 <span data-ttu-id="b6f9a-111">Если смещение изображения нативного изображения находится в пределах общего времени выполнения языка (CLR), точка разрыва будет проигнорирована.</span><span class="sxs-lookup"><span data-stu-id="b6f9a-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="b6f9a-112">Это позволяет CLR избежать отправки внеполосной точки разрыва, когда точка разрыва устанавливается отладчиком.</span><span class="sxs-lookup"><span data-stu-id="b6f9a-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6f9a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b6f9a-113">Requirements</span></span>  
 <span data-ttu-id="b6f9a-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6f9a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6f9a-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6f9a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6f9a-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6f9a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6f9a-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6f9a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
