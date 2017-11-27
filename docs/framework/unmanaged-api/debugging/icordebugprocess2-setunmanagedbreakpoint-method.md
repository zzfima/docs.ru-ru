---
title: "Метод ICorDebugProcess2::SetUnmanagedBreakpoint"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.SetUnmanagedBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dd2d6ac2967b4314a57aa30bbb34ff3d354a6365
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="66d3f-102">Метод ICorDebugProcess2::SetUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="66d3f-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="66d3f-103">Задает неуправляемую точку останова с позиции указанного образа в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="66d3f-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66d3f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66d3f-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66d3f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66d3f-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="66d3f-106">[in] Объект `CORDB_ADDRESS` , указывающий смещение образов в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="66d3f-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="66d3f-107">[in] Размер в байтах для `buffer` массива.</span><span class="sxs-lookup"><span data-stu-id="66d3f-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="66d3f-108">[out] Массив, содержащий код операции, который заменяется точки останова.</span><span class="sxs-lookup"><span data-stu-id="66d3f-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="66d3f-109">[out] Указатель на число байтов, возвращенных в `buffer` массива.</span><span class="sxs-lookup"><span data-stu-id="66d3f-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66d3f-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="66d3f-110">Remarks</span></span>  
 <span data-ttu-id="66d3f-111">Если смещение образа в машинном коде в общеязыковой среде выполнения (CLR), точка останова будет игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="66d3f-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="66d3f-112">Это позволяет среде CLR избежать диспетчеризации точки останова по внешнему каналу, когда задана точка останова в отладчике.</span><span class="sxs-lookup"><span data-stu-id="66d3f-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66d3f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="66d3f-113">Requirements</span></span>  
 <span data-ttu-id="66d3f-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66d3f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66d3f-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66d3f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66d3f-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66d3f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66d3f-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66d3f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
