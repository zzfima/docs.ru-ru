---
title: "Метод ICorDebugProcess6::GetExportStepInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dbb0e1cf904675005522002596476aec996124b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="53b97-102">Метод ICorDebugProcess6::GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="53b97-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="53b97-103">Предоставляет информацию о функциях, экспортируемых в ходе выполнения, для пошагового перемещения по управляемому коду.</span><span class="sxs-lookup"><span data-stu-id="53b97-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53b97-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53b97-104">Syntax</span></span>  
  
```  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53b97-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="53b97-105">Parameters</span></span>  
 <span data-ttu-id="53b97-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="53b97-106">pszExportName</span></span>  
 <span data-ttu-id="53b97-107">[входной] Имя функции экспорта во время выполнения, записываемой в таблице экспорта PE.</span><span class="sxs-lookup"><span data-stu-id="53b97-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="53b97-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="53b97-108">invokeKind</span></span>  
 <span data-ttu-id="53b97-109">[out] Указатель на член [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) перечисление, которое описывает, каким образом экспортируемая функция будет вызывать управляемый код.</span><span class="sxs-lookup"><span data-stu-id="53b97-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="53b97-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="53b97-110">invokePurpose</span></span>  
 <span data-ttu-id="53b97-111">[out] Указатель на член [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) перечисление, описывающее, почему экспортируемая функция будет вызывать управляемый код.</span><span class="sxs-lookup"><span data-stu-id="53b97-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53b97-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="53b97-112">Return Value</span></span>  
 <span data-ttu-id="53b97-113">Метод может возвращать значения, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="53b97-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="53b97-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="53b97-114">Return value</span></span>|<span data-ttu-id="53b97-115">Описание</span><span class="sxs-lookup"><span data-stu-id="53b97-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="53b97-116">Успешный вызов метода.</span><span class="sxs-lookup"><span data-stu-id="53b97-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="53b97-117">`pInvokeKind`или `pInvokePurpose` — **null**.</span><span class="sxs-lookup"><span data-stu-id="53b97-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="53b97-118">Другие ошибочные значения `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="53b97-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="53b97-119">По мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="53b97-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53b97-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="53b97-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53b97-121">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="53b97-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53b97-122">Требования</span><span class="sxs-lookup"><span data-stu-id="53b97-122">Requirements</span></span>  
 <span data-ttu-id="53b97-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53b97-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53b97-124">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53b97-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53b97-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53b97-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53b97-126">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53b97-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53b97-127">См. также</span><span class="sxs-lookup"><span data-stu-id="53b97-127">See Also</span></span>  
 [<span data-ttu-id="53b97-128">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="53b97-128">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="53b97-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="53b97-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
