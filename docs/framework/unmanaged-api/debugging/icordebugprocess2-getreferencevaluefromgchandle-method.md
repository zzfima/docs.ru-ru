---
title: Метод ICorDebugProcess2::GetReferenceValueFromGCHandle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f38f9a3ebd88e0a5abb7a6bc8cb4026dc7d0f068
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736935"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="bd1f8-102">Метод ICorDebugProcess2::GetReferenceValueFromGCHandle</span><span class="sxs-lookup"><span data-stu-id="bd1f8-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="bd1f8-103">Получает указатель ссылки на указанный управляемый объект, с дескриптором сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd1f8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd1f8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd1f8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bd1f8-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="bd1f8-106">[in] Указатель на управляемый объект, имеющий дескриптор сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="bd1f8-107">Это значение равно <xref:System.IntPtr> объекта и могут быть получены из <xref:System.Runtime.InteropServices.GCHandle> для управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="bd1f8-108">[out] Указатель на адрес ICorDebugReferenceValue объект, представляющий ссылку на указанный управляемый объект.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd1f8-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="bd1f8-109">Remarks</span></span>  
 <span data-ttu-id="bd1f8-110">Не следует путать возвращенное значение ссылки со значением ссылки сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="bd1f8-111">Возвращаемая ссылка ведет себя как обычной ссылки.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="bd1f8-112">Этот параметр отключен, когда выполнение кода продолжается после точки останова.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="bd1f8-113">Время существования целевого объекта не зависит от времени существования значения ссылки.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd1f8-114">`GetReferenceValueFromGCHandle` Метод не проверяет маркер.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="bd1f8-115">Таким образом `GetReferenceValueFromGCHandle` метода может привести к повреждению отладчика и отлаживаемого, если передается недопустимый дескриптор кода.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd1f8-116">Требования</span><span class="sxs-lookup"><span data-stu-id="bd1f8-116">Requirements</span></span>  
 <span data-ttu-id="bd1f8-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd1f8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd1f8-118">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd1f8-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd1f8-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd1f8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd1f8-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd1f8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
