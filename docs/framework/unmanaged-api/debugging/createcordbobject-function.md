---
title: Функция CreateCordbObject
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ab86277956469e558d20cea81174a7fdcc0020b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739336"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="ea465-102">Функция CreateCordbObject</span><span class="sxs-lookup"><span data-stu-id="ea465-102">CreateCordbObject Function</span></span>
<span data-ttu-id="ea465-103">Создает интерфейс отладчика ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)), обеспечивающий функциональность для создания управляемого сеанса отладки в удаленном процессе.</span><span class="sxs-lookup"><span data-stu-id="ea465-103">Creates a debugger interface ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea465-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea465-104">Syntax</span></span>  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea465-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ea465-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="ea465-106">[in] Версия отладчика целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="ea465-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="ea465-107">Для удаленной отладки этот параметр должен иметь значение CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="ea465-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="ea465-108">[out] Указатель на указатель на объект, который приводится к [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) интерфейс и возвращается.</span><span class="sxs-lookup"><span data-stu-id="ea465-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea465-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ea465-109">Return Value</span></span>  
 <span data-ttu-id="ea465-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ea465-110">S_OK</span></span>  
 <span data-ttu-id="ea465-111">Количество сред CLR в процессе успешно определено, и соответствующие массивы дескрипторов и путей заполнены должным образом.</span><span class="sxs-lookup"><span data-stu-id="ea465-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="ea465-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ea465-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="ea465-113">Параметр `ppCordb` имеет значение null, или параметр `iDebuggerVersion` не имеет значение CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="ea465-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="ea465-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ea465-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="ea465-115">Не удается выделить достаточно памяти для `ppCordb`.</span><span class="sxs-lookup"><span data-stu-id="ea465-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="ea465-116">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="ea465-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="ea465-117">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="ea465-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea465-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea465-118">Remarks</span></span>  
 <span data-ttu-id="ea465-119">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) интерфейс, который возвращается в `ppCordb` — это интерфейс верхнего уровня отладки для всех управляемых служб отладки.</span><span class="sxs-lookup"><span data-stu-id="ea465-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea465-120">Требования</span><span class="sxs-lookup"><span data-stu-id="ea465-120">Requirements</span></span>  
 <span data-ttu-id="ea465-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea465-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea465-122">**Заголовок.** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="ea465-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="ea465-123">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="ea465-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="ea465-124">**Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="ea465-124">**.NET Framework Versions:** 3.5 SP1</span></span>
