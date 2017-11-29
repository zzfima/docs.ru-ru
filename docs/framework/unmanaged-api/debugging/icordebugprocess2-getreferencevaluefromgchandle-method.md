---
title: "Метод ICorDebugProcess2::GetReferenceValueFromGCHandle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d40d1799a7c1572e8213fda3a163fb9a84060f92
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="4f865-102">Метод ICorDebugProcess2::GetReferenceValueFromGCHandle</span><span class="sxs-lookup"><span data-stu-id="4f865-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="4f865-103">Получает указатель ссылки на указанный управляемый объект, с дескриптором сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4f865-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f865-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f865-104">Syntax</span></span>  
  
```  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f865-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f865-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="4f865-106">[in] Указатель на управляемый объект, который имеет дескриптор сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4f865-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="4f865-107">Это значение является <xref:System.IntPtr> объекта и может быть извлечен из <xref:System.Runtime.InteropServices.GCHandle> для управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="4f865-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="4f865-108">[out] Указатель на адрес объекта ICorDebugReferenceValue, представляющий ссылку на указанный управляемый объект.</span><span class="sxs-lookup"><span data-stu-id="4f865-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f865-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f865-109">Remarks</span></span>  
 <span data-ttu-id="4f865-110">Не следует путать возвращенное значение ссылки со значением коллекции ссылка сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4f865-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="4f865-111">Возвращаемая ссылка ведет себя как обычной ссылки.</span><span class="sxs-lookup"><span data-stu-id="4f865-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="4f865-112">Этот параметр отключен, когда выполнение кода продолжается после точки останова.</span><span class="sxs-lookup"><span data-stu-id="4f865-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="4f865-113">Время существования целевого объекта не зависит от времени существования значения ссылки.</span><span class="sxs-lookup"><span data-stu-id="4f865-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f865-114">`GetReferenceValueFromGCHandle` Метод не проверяет дескриптор.</span><span class="sxs-lookup"><span data-stu-id="4f865-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="4f865-115">Таким образом `GetReferenceValueFromGCHandle` метода может привести к повреждению отладчика и отлаживаемого, если передается недопустимый дескриптор кода.</span><span class="sxs-lookup"><span data-stu-id="4f865-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f865-116">Требования</span><span class="sxs-lookup"><span data-stu-id="4f865-116">Requirements</span></span>  
 <span data-ttu-id="4f865-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f865-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f865-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f865-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f865-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f865-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f865-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f865-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
