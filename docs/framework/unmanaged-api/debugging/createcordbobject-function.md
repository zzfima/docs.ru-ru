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
ms.openlocfilehash: 12898f75d2575e539b018ea367bc870a3dc738a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406335"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="4a9e5-102">Функция CreateCordbObject</span><span class="sxs-lookup"><span data-stu-id="4a9e5-102">CreateCordbObject Function</span></span>
<span data-ttu-id="4a9e5-103">Создает интерфейс отладчика ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)), обеспечивающий функциональность для создания управляемого сеанса отладки в удаленном процессе.</span><span class="sxs-lookup"><span data-stu-id="4a9e5-103">Creates a debugger interface ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a9e5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a9e5-104">Syntax</span></span>  
  
```  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a9e5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4a9e5-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="4a9e5-106">[in] Версия отладчика целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="4a9e5-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="4a9e5-107">Для удаленной отладки этот параметр должен иметь значение CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="4a9e5-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="4a9e5-108">[out] Указатель на указатель на объект, который будет приведен к [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) и возвращаться.</span><span class="sxs-lookup"><span data-stu-id="4a9e5-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a9e5-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4a9e5-109">Return Value</span></span>  
 <span data-ttu-id="4a9e5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a9e5-110">S_OK</span></span>  
 <span data-ttu-id="4a9e5-111">Количество сред CLR в процессе успешно определено, и соответствующие массивы дескрипторов и путей заполнены должным образом.</span><span class="sxs-lookup"><span data-stu-id="4a9e5-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="4a9e5-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4a9e5-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="4a9e5-113">Параметр `ppCordb` имеет значение null, или параметр `iDebuggerVersion` не имеет значение CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="4a9e5-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="4a9e5-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4a9e5-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="4a9e5-115">Не удается выделить достаточно памяти для `ppCordb`.</span><span class="sxs-lookup"><span data-stu-id="4a9e5-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="4a9e5-116">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="4a9e5-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="4a9e5-117">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="4a9e5-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a9e5-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="4a9e5-118">Remarks</span></span>  
 <span data-ttu-id="4a9e5-119">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) интерфейс, который возвращается в `ppCordb` является интерфейсом верхнего уровня отладки для всех управляемых служб отладки.</span><span class="sxs-lookup"><span data-stu-id="4a9e5-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a9e5-120">Требования</span><span class="sxs-lookup"><span data-stu-id="4a9e5-120">Requirements</span></span>  
 <span data-ttu-id="4a9e5-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a9e5-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a9e5-122">**Заголовок:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="4a9e5-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="4a9e5-123">**Библиотека:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="4a9e5-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="4a9e5-124">**Версии платформы .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="4a9e5-124">**.NET Framework Versions:** 3.5 SP1</span></span>
