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
ms.openlocfilehash: d21e0d3d0370ec7c1b223be29099f6b99822463b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132109"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="9508d-102">Функция CreateCordbObject</span><span class="sxs-lookup"><span data-stu-id="9508d-102">CreateCordbObject Function</span></span>
<span data-ttu-id="9508d-103">Создает интерфейс отладчика ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)), который предоставляет функциональные возможности для создания экземпляра управляемого сеанса отладки на удаленном процессе.</span><span class="sxs-lookup"><span data-stu-id="9508d-103">Creates a debugger interface ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9508d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9508d-104">Syntax</span></span>  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9508d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9508d-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="9508d-106">[in] Версия отладчика целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="9508d-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="9508d-107">Для удаленной отладки этот параметр должен иметь значение CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="9508d-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="9508d-108">заполняет Указатель на указатель на объект, который будет приведен к интерфейсу [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) и возвращен.</span><span class="sxs-lookup"><span data-stu-id="9508d-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9508d-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9508d-109">Return Value</span></span>  
 <span data-ttu-id="9508d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9508d-110">S_OK</span></span>  
 <span data-ttu-id="9508d-111">Количество сред CLR в процессе успешно определено, и соответствующие массивы дескрипторов и путей заполнены должным образом.</span><span class="sxs-lookup"><span data-stu-id="9508d-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="9508d-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9508d-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="9508d-113">Параметр `ppCordb` имеет значение null, или параметр `iDebuggerVersion` не имеет значение CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="9508d-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="9508d-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9508d-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="9508d-115">Не удается выделить достаточно памяти для `ppCordb`.</span><span class="sxs-lookup"><span data-stu-id="9508d-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="9508d-116">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="9508d-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9508d-117">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="9508d-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9508d-118">Заметки</span><span class="sxs-lookup"><span data-stu-id="9508d-118">Remarks</span></span>  
 <span data-ttu-id="9508d-119">Интерфейс [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , возвращаемый в `ppCordb`, является интерфейсом отладки верхнего уровня для всех управляемых служб отладки.</span><span class="sxs-lookup"><span data-stu-id="9508d-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9508d-120">Требования</span><span class="sxs-lookup"><span data-stu-id="9508d-120">Requirements</span></span>  
 <span data-ttu-id="9508d-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9508d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9508d-122">**Заголовок:** Кореклрремотедебуггингинтерфацес. h</span><span class="sxs-lookup"><span data-stu-id="9508d-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="9508d-123">**Библиотека:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="9508d-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="9508d-124">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="9508d-124">**.NET Framework Versions:** 3.5 SP1</span></span>
