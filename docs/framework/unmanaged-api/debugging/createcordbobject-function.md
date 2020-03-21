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
ms.openlocfilehash: 2716adcc8c79c8003202561ea2011c2469a6bc5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179231"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="25b57-102">Функция CreateCordbObject</span><span class="sxs-lookup"><span data-stu-id="25b57-102">CreateCordbObject Function</span></span>
<span data-ttu-id="25b57-103">Создает интерфейс отладчика[(ICorDebug),](icordebug-interface.md)который предоставляет функциональность для мгновенного сеанса управляемой отладки в удаленном процессе.</span><span class="sxs-lookup"><span data-stu-id="25b57-103">Creates a debugger interface ([ICorDebug](icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25b57-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25b57-104">Syntax</span></span>  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25b57-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="25b57-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="25b57-106">[in] Версия отладчика целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="25b57-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="25b57-107">Для удаленной отладки этот параметр должен иметь значение CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="25b57-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="25b57-108">(ваут) Указатель на указатель на объект, который будет отлит на интерфейс [ICorDebug](icordebug-interface.md) и возвращен.</span><span class="sxs-lookup"><span data-stu-id="25b57-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25b57-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="25b57-109">Return Value</span></span>  
 <span data-ttu-id="25b57-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="25b57-110">S_OK</span></span>  
 <span data-ttu-id="25b57-111">Количество сред CLR в процессе успешно определено, и соответствующие массивы дескрипторов и путей заполнены должным образом.</span><span class="sxs-lookup"><span data-stu-id="25b57-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="25b57-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="25b57-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="25b57-113">Параметр `ppCordb` имеет значение null, или параметр `iDebuggerVersion` не имеет значение CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="25b57-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="25b57-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="25b57-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="25b57-115">Не удается выделить достаточно памяти для `ppCordb`.</span><span class="sxs-lookup"><span data-stu-id="25b57-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="25b57-116">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="25b57-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="25b57-117">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="25b57-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25b57-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="25b57-118">Remarks</span></span>  
 <span data-ttu-id="25b57-119">Возвращается интерфейс [ICorDebug](icordebug-interface.md) `ppCordb` для всех управляемых служб отладки.</span><span class="sxs-lookup"><span data-stu-id="25b57-119">The [ICorDebug](icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25b57-120">Требования</span><span class="sxs-lookup"><span data-stu-id="25b57-120">Requirements</span></span>  
 <span data-ttu-id="25b57-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25b57-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25b57-122">**Заголовок:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="25b57-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="25b57-123">**Библиотека:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="25b57-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="25b57-124">**Рамочные версии .NET:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="25b57-124">**.NET Framework Versions:** 3.5 SP1</span></span>
