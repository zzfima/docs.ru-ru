---
title: Метод ICorDebugHeapValue2::CreateHandle
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
ms.openlocfilehash: c7a1bf3cb10cbc8cdae2788b45e1badaf66a9dbd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178879"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="ffe9e-102">Метод ICorDebugHeapValue2::CreateHandle</span><span class="sxs-lookup"><span data-stu-id="ffe9e-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="ffe9e-103">Создает ручку указанного типа для значения кучи, представленного этим объектом ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="ffe9e-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffe9e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffe9e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffe9e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ffe9e-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="ffe9e-106">(в) Значение перечисления CorDebugHandleType, которое определяет тип создаваемых рукояток.</span><span class="sxs-lookup"><span data-stu-id="ffe9e-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="ffe9e-107">(ваут) Указатель на адрес объекта ICorDebugHandleValue, который представляет новую ручку для этого значения кучи.</span><span class="sxs-lookup"><span data-stu-id="ffe9e-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffe9e-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="ffe9e-108">Remarks</span></span>  
 <span data-ttu-id="ffe9e-109">Ручка будет создана в домене приложения, связанном со значением кучи, и станет недействительной, если домен приложения будет разгружен.</span><span class="sxs-lookup"><span data-stu-id="ffe9e-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="ffe9e-110">Несколько вызовов к этой функции для одного и того же значения кучи создаст несколько рукояток.</span><span class="sxs-lookup"><span data-stu-id="ffe9e-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="ffe9e-111">Поскольку ручки влияют на производительность сборщика мусора, отладчик должен ограничиваться относительно небольшим числом ручек (около 256), которые активны одновременно.</span><span class="sxs-lookup"><span data-stu-id="ffe9e-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffe9e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ffe9e-112">Requirements</span></span>  
 <span data-ttu-id="ffe9e-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffe9e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffe9e-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ffe9e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ffe9e-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffe9e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffe9e-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffe9e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
