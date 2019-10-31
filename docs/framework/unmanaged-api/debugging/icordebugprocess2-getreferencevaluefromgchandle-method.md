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
ms.openlocfilehash: 47647bf0460507b4c88b47bf87bfcc3bf620aecc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137221"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="50fac-102">Метод ICorDebugProcess2::GetReferenceValueFromGCHandle</span><span class="sxs-lookup"><span data-stu-id="50fac-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="50fac-103">Возвращает указатель ссылки на указанный управляемый объект, который имеет обработчик сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="50fac-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50fac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50fac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50fac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="50fac-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="50fac-106">окне Указатель на управляемый объект, который имеет обработчик сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="50fac-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="50fac-107">Это значение является <xref:System.IntPtr> объектом и может быть получено из <xref:System.Runtime.InteropServices.GCHandle> для управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="50fac-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="50fac-108">заполняет Указатель на адрес объекта ICorDebugReferenceValue, который представляет ссылку на указанный управляемый объект.</span><span class="sxs-lookup"><span data-stu-id="50fac-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50fac-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="50fac-109">Remarks</span></span>  
 <span data-ttu-id="50fac-110">Не путайте возвращаемое ссылочное значение со ссылочным значением сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="50fac-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="50fac-111">Возвращаемая ссылка ведет себя как обычная ссылка.</span><span class="sxs-lookup"><span data-stu-id="50fac-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="50fac-112">Он отключен, когда выполнение кода продолжится после точки останова.</span><span class="sxs-lookup"><span data-stu-id="50fac-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="50fac-113">Время существования целевого объекта не зависит от времени существования ссылочного значения.</span><span class="sxs-lookup"><span data-stu-id="50fac-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50fac-114">Метод `GetReferenceValueFromGCHandle` не проверяет этот обработчик.</span><span class="sxs-lookup"><span data-stu-id="50fac-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="50fac-115">Поэтому метод `GetReferenceValueFromGCHandle` может привести к повреждению отладчика и отлаживаемого кода при передаче недопустимого маркера.</span><span class="sxs-lookup"><span data-stu-id="50fac-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50fac-116">Требования</span><span class="sxs-lookup"><span data-stu-id="50fac-116">Requirements</span></span>  
 <span data-ttu-id="50fac-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50fac-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50fac-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50fac-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50fac-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50fac-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50fac-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50fac-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
