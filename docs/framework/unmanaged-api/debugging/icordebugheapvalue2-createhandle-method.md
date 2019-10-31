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
ms.openlocfilehash: b9eab1274f2d0ad562c0dec6adeddb85c6cfc458
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138383"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="e8c46-102">Метод ICorDebugHeapValue2::CreateHandle</span><span class="sxs-lookup"><span data-stu-id="e8c46-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="e8c46-103">Создает маркер указанного типа для значения кучи, представленного этим объектом ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="e8c46-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8c46-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8c46-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8c46-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e8c46-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="e8c46-106">окне Значение перечисления Кордебугхандлетипе, указывающее тип создаваемого обработчика.</span><span class="sxs-lookup"><span data-stu-id="e8c46-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="e8c46-107">заполняет Указатель на адрес объекта ICorDebugHandleValue, который представляет новый маркер для этого значения кучи.</span><span class="sxs-lookup"><span data-stu-id="e8c46-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8c46-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="e8c46-108">Remarks</span></span>  
 <span data-ttu-id="e8c46-109">Этот маркер будет создан в домене приложения, связанном со значением кучи, и станет недействительным при выгрузке домена приложения.</span><span class="sxs-lookup"><span data-stu-id="e8c46-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="e8c46-110">Несколько вызовов этой функции для одного значения кучи будут создавать несколько дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="e8c46-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="e8c46-111">Поскольку дескрипторы влияют на производительность сборщика мусора, отладчик должен ограничиваться относительно небольшим количеством дескрипторов (около 256), которые активны за один раз.</span><span class="sxs-lookup"><span data-stu-id="e8c46-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8c46-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e8c46-112">Requirements</span></span>  
 <span data-ttu-id="e8c46-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8c46-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8c46-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8c46-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8c46-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8c46-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8c46-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8c46-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
