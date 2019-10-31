---
title: Функция CreateDebuggingInterfaceFromVersion Silverlight
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
ms.openlocfilehash: 438af9f191f48a86207c3b343ba428eef2c1fabc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132201"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="9344c-102">Функция CreateDebuggingInterfaceFromVersion Silverlight</span><span class="sxs-lookup"><span data-stu-id="9344c-102">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>
<span data-ttu-id="9344c-103">Принимает строку версии среды CLR, возвращаемую [функцией CreateVersionStringFromModule](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md), и возвращает соответствующий интерфейс отладчика (как правило, [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="9344c-103">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9344c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9344c-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9344c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9344c-105">Parameters</span></span>  
 `szDebuggeeVersion`  
 <span data-ttu-id="9344c-106">окне Строка версии среды CLR в целевом отлаживаемом объекте, возвращаемом [функцией CreateVersionStringFromModule](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md).</span><span class="sxs-lookup"><span data-stu-id="9344c-106">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="9344c-107">[out] Указатель на COM-объект (`IUnknown`).</span><span class="sxs-lookup"><span data-stu-id="9344c-107">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="9344c-108">Перед возвращением этот объект будет приведен к объекту [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9344c-108">This object will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9344c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9344c-109">Return Value</span></span>  
 <span data-ttu-id="9344c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9344c-110">S_OK</span></span>  
 <span data-ttu-id="9344c-111">`ppCordb` ссылается на допустимый объект, реализующий интерфейс [интерфейса ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9344c-111">`ppCordb` references a valid object that implements the [ICorDebug interface](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface.</span></span>  
  
 <span data-ttu-id="9344c-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9344c-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="9344c-113">Либо `szDebuggeeVersion`, либо `ppCordb` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="9344c-113">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 <span data-ttu-id="9344c-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span><span class="sxs-lookup"><span data-stu-id="9344c-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span></span>  
 <span data-ttu-id="9344c-115">Не удалось найти компонент, который необходим для отладки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9344c-115">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="9344c-116">Это означает, что не удалось найти mscordbi.dll или mscordaccore.dll в каталоге, где находится целевой объект CoreCLR.dll.</span><span class="sxs-lookup"><span data-stu-id="9344c-116">This means that either mscordbi.dll or mscordaccore.dll was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="9344c-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span><span class="sxs-lookup"><span data-stu-id="9344c-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span></span>  
 <span data-ttu-id="9344c-118">Версия mscordbi.dll или mscordaccore.dll не совпадает с версией целевого объекта CoreCLR.dll.</span><span class="sxs-lookup"><span data-stu-id="9344c-118">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="9344c-119">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="9344c-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9344c-120">Не удалось вернуть [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9344c-120">Unable to return an [ICorDebug interface](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9344c-121">Заметки</span><span class="sxs-lookup"><span data-stu-id="9344c-121">Remarks</span></span>  
 <span data-ttu-id="9344c-122">Возвращаемый интерфейс предоставляет средства для подключения к среде CLR в целевом процессе и отладки управляемого кода, который выполняется в этой среде CLR.</span><span class="sxs-lookup"><span data-stu-id="9344c-122">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9344c-123">Требования</span><span class="sxs-lookup"><span data-stu-id="9344c-123">Requirements</span></span>  
 <span data-ttu-id="9344c-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9344c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9344c-125">**Заголовок:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="9344c-125">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="9344c-126">**Библиотека:** dbgshim. dll</span><span class="sxs-lookup"><span data-stu-id="9344c-126">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="9344c-127">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="9344c-127">**.NET Framework Versions:** 3.5 SP1</span></span>
