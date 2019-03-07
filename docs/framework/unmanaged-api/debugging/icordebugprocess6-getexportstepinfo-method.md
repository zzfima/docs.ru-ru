---
title: Метод ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b60bad75cb6286bda026e5b67e0a4fa8e2347dd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487178"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="f295a-102">Метод ICorDebugProcess6::GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="f295a-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="f295a-103">Предоставляет информацию о функциях, экспортируемых в ходе выполнения, для пошагового перемещения по управляемому коду.</span><span class="sxs-lookup"><span data-stu-id="f295a-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f295a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f295a-104">Syntax</span></span>  
  
```  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f295a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f295a-105">Parameters</span></span>  
 <span data-ttu-id="f295a-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="f295a-106">pszExportName</span></span>  
 <span data-ttu-id="f295a-107">[входной] Имя функции экспорта во время выполнения, записываемой в таблице экспорта PE.</span><span class="sxs-lookup"><span data-stu-id="f295a-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="f295a-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="f295a-108">invokeKind</span></span>  
 <span data-ttu-id="f295a-109">[out] Указатель на член [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) перечисление, описывающее, каким образом экспортируемая функция будет вызывать управляемый код.</span><span class="sxs-lookup"><span data-stu-id="f295a-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="f295a-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="f295a-110">invokePurpose</span></span>  
 <span data-ttu-id="f295a-111">[out] Указатель на член [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) перечисление, описывающее, почему экспортируемая функция будет вызывать управляемый код.</span><span class="sxs-lookup"><span data-stu-id="f295a-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f295a-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f295a-112">Return Value</span></span>  
 <span data-ttu-id="f295a-113">Метод может возвращать значения, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f295a-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="f295a-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f295a-114">Return value</span></span>|<span data-ttu-id="f295a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f295a-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="f295a-116">Успешный вызов метода.</span><span class="sxs-lookup"><span data-stu-id="f295a-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="f295a-117">`pInvokeKind` или `pInvokePurpose` — **null**.</span><span class="sxs-lookup"><span data-stu-id="f295a-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="f295a-118">Другие ошибочные значения `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="f295a-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="f295a-119">По мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="f295a-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f295a-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="f295a-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f295a-121">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="f295a-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f295a-122">Требования</span><span class="sxs-lookup"><span data-stu-id="f295a-122">Requirements</span></span>  
 <span data-ttu-id="f295a-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f295a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f295a-124">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f295a-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f295a-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f295a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f295a-126">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f295a-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f295a-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f295a-127">See also</span></span>
- [<span data-ttu-id="f295a-128">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="f295a-128">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="f295a-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f295a-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
