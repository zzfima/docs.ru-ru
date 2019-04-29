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
ms.openlocfilehash: f546d7707c40f7f26a46177ae972a988e54e1e45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965838"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="5ea9a-102">Функция CreateCordbObject</span><span class="sxs-lookup"><span data-stu-id="5ea9a-102">CreateCordbObject Function</span></span>
<span data-ttu-id="5ea9a-103">Создает интерфейс отладчика ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)), обеспечивающий функциональность для создания управляемого сеанса отладки в удаленном процессе.</span><span class="sxs-lookup"><span data-stu-id="5ea9a-103">Creates a debugger interface ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ea9a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ea9a-104">Syntax</span></span>  
  
```  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ea9a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ea9a-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="5ea9a-106">[in] Версия отладчика целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="5ea9a-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="5ea9a-107">Для удаленной отладки этот параметр должен иметь значение CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="5ea9a-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="5ea9a-108">[out] Указатель на указатель на объект, который приводится к [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) интерфейс и возвращается.</span><span class="sxs-lookup"><span data-stu-id="5ea9a-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ea9a-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5ea9a-109">Return Value</span></span>  
 <span data-ttu-id="5ea9a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5ea9a-110">S_OK</span></span>  
 <span data-ttu-id="5ea9a-111">Количество сред CLR в процессе успешно определено, и соответствующие массивы дескрипторов и путей заполнены должным образом.</span><span class="sxs-lookup"><span data-stu-id="5ea9a-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="5ea9a-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5ea9a-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="5ea9a-113">Параметр `ppCordb` имеет значение null, или параметр `iDebuggerVersion` не имеет значение CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="5ea9a-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="5ea9a-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5ea9a-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="5ea9a-115">Не удается выделить достаточно памяти для `ppCordb`.</span><span class="sxs-lookup"><span data-stu-id="5ea9a-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="5ea9a-116">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="5ea9a-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="5ea9a-117">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="5ea9a-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ea9a-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="5ea9a-118">Remarks</span></span>  
 <span data-ttu-id="5ea9a-119">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) интерфейс, который возвращается в `ppCordb` — это интерфейс верхнего уровня отладки для всех управляемых служб отладки.</span><span class="sxs-lookup"><span data-stu-id="5ea9a-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ea9a-120">Требования</span><span class="sxs-lookup"><span data-stu-id="5ea9a-120">Requirements</span></span>  
 <span data-ttu-id="5ea9a-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ea9a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ea9a-122">**Заголовок.** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="5ea9a-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="5ea9a-123">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="5ea9a-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="5ea9a-124">**Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="5ea9a-124">**.NET Framework Versions:** 3.5 SP1</span></span>
