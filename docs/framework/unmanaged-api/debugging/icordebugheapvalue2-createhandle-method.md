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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 078dfd7162c250f0279b8bc372aeb39662aa0119
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498540"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="d5f6e-102">Метод ICorDebugHeapValue2::CreateHandle</span><span class="sxs-lookup"><span data-stu-id="d5f6e-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="d5f6e-103">Создает дескриптор указанного типа для значения кучи, представленный этим объектом ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="d5f6e-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5f6e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5f6e-104">Syntax</span></span>  
  
```  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5f6e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d5f6e-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="d5f6e-106">[in] Значение перечисления CorDebugHandleType, которое указывает тип дескриптора.</span><span class="sxs-lookup"><span data-stu-id="d5f6e-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="d5f6e-107">[out] Указатель на адрес ICorDebugHandleValue объект, представляющий новый маркер для этого значения кучи.</span><span class="sxs-lookup"><span data-stu-id="d5f6e-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5f6e-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="d5f6e-108">Remarks</span></span>  
 <span data-ttu-id="d5f6e-109">Дескриптор будет создан в домене приложения, который связан со значением кучи и станет недействительным, если выгрузки домена приложения.</span><span class="sxs-lookup"><span data-stu-id="d5f6e-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="d5f6e-110">Несколько вызовов этой функции для одного значения кучи создаст несколько дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="d5f6e-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="d5f6e-111">Так как дескрипторы влияют на производительность сборщика мусора, отладчик должен задать ограничение относительно небольшое количество дескрипторов (около 256), которые активны одновременно.</span><span class="sxs-lookup"><span data-stu-id="d5f6e-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5f6e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d5f6e-112">Requirements</span></span>  
 <span data-ttu-id="d5f6e-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5f6e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5f6e-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5f6e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5f6e-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5f6e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5f6e-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5f6e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
