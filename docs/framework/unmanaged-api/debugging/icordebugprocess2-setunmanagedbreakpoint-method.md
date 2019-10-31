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
ms.openlocfilehash: ffab2762fd86e95c3272ca456039028e0897bc41
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137181"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="87934-102">Метод ICorDebugProcess2::SetUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="87934-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="87934-103">Задает неуправляемую точку останова в указанном смещении машинного образа.</span><span class="sxs-lookup"><span data-stu-id="87934-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87934-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87934-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87934-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="87934-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="87934-106">окне Объект `CORDB_ADDRESS`, указывающий смещение машинного образа.</span><span class="sxs-lookup"><span data-stu-id="87934-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="87934-107">окне Размер массива `buffer` в байтах.</span><span class="sxs-lookup"><span data-stu-id="87934-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="87934-108">заполняет Массив, содержащий код операции, который заменяется точкой останова.</span><span class="sxs-lookup"><span data-stu-id="87934-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="87934-109">заполняет Указатель на число байтов, возвращенных в массиве `buffer`.</span><span class="sxs-lookup"><span data-stu-id="87934-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87934-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="87934-110">Remarks</span></span>  
 <span data-ttu-id="87934-111">Если смещение машинного образа находится в среде CLR, точка останова будет пропущена.</span><span class="sxs-lookup"><span data-stu-id="87934-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="87934-112">Это позволяет среде CLR избежать диспетчеризации точки останова по внешнему каналу, когда точка останова задается отладчиком.</span><span class="sxs-lookup"><span data-stu-id="87934-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87934-113">Требования</span><span class="sxs-lookup"><span data-stu-id="87934-113">Requirements</span></span>  
 <span data-ttu-id="87934-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87934-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87934-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87934-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87934-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87934-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87934-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87934-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
