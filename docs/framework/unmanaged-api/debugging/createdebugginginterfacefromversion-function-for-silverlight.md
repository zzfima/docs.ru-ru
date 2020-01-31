---
title: Функция CreateDebuggingInterfaceFromVersion для Silverlight
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
ms.openlocfilehash: 85b5a5a630f399d0e036de434365e2e4f8f02dea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793827"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="9bf40-102">Функция CreateDebuggingInterfaceFromVersion для Silverlight</span><span class="sxs-lookup"><span data-stu-id="9bf40-102">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>
<span data-ttu-id="9bf40-103">Принимает строку версии среды CLR, возвращаемую [функцией CreateVersionStringFromModule](createversionstringfrommodule-function.md), и возвращает соответствующий интерфейс отладчика (как правило, [ICorDebug](icordebug-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="9bf40-103">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bf40-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9bf40-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bf40-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9bf40-105">Parameters</span></span>  
 `szDebuggeeVersion`  
 <span data-ttu-id="9bf40-106">окне Строка версии среды CLR в целевом отлаживаемом объекте, возвращаемом [функцией CreateVersionStringFromModule](createversionstringfrommodule-function.md).</span><span class="sxs-lookup"><span data-stu-id="9bf40-106">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="9bf40-107">[out] Указатель на COM-объект (`IUnknown`).</span><span class="sxs-lookup"><span data-stu-id="9bf40-107">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="9bf40-108">Перед возвращением этот объект будет приведен к объекту [ICorDebug](icordebug-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9bf40-108">This object will be cast to an [ICorDebug](icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9bf40-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9bf40-109">Return Value</span></span>  
 <span data-ttu-id="9bf40-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9bf40-110">S_OK</span></span>  
 <span data-ttu-id="9bf40-111">`ppCordb` ссылается на допустимый объект, реализующий интерфейс [интерфейса ICorDebug](icordebug-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9bf40-111">`ppCordb` references a valid object that implements the [ICorDebug interface](icordebug-interface.md) interface.</span></span>  
  
 <span data-ttu-id="9bf40-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9bf40-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="9bf40-113">Либо `szDebuggeeVersion`, либо `ppCordb` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="9bf40-113">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 <span data-ttu-id="9bf40-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span><span class="sxs-lookup"><span data-stu-id="9bf40-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span></span>  
 <span data-ttu-id="9bf40-115">Не удалось найти компонент, который необходим для отладки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9bf40-115">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="9bf40-116">Это означает, что не удалось найти mscordbi.dll или mscordaccore.dll в каталоге, где находится целевой объект CoreCLR.dll.</span><span class="sxs-lookup"><span data-stu-id="9bf40-116">This means that either mscordbi.dll or mscordaccore.dll was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="9bf40-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span><span class="sxs-lookup"><span data-stu-id="9bf40-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span></span>  
 <span data-ttu-id="9bf40-118">Версия mscordbi.dll или mscordaccore.dll не совпадает с версией целевого объекта CoreCLR.dll.</span><span class="sxs-lookup"><span data-stu-id="9bf40-118">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="9bf40-119">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="9bf40-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9bf40-120">Не удалось вернуть [Интерфейс ICorDebug](icordebug-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9bf40-120">Unable to return an [ICorDebug interface](icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bf40-121">Заметки</span><span class="sxs-lookup"><span data-stu-id="9bf40-121">Remarks</span></span>  
 <span data-ttu-id="9bf40-122">Возвращаемый интерфейс предоставляет средства для подключения к среде CLR в целевом процессе и отладки управляемого кода, который выполняется в этой среде CLR.</span><span class="sxs-lookup"><span data-stu-id="9bf40-122">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bf40-123">Требования</span><span class="sxs-lookup"><span data-stu-id="9bf40-123">Requirements</span></span>  
 <span data-ttu-id="9bf40-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bf40-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bf40-125">**Заголовок:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="9bf40-125">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="9bf40-126">**Библиотека:** dbgshim. dll</span><span class="sxs-lookup"><span data-stu-id="9bf40-126">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="9bf40-127">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="9bf40-127">**.NET Framework Versions:** 3.5 SP1</span></span>
