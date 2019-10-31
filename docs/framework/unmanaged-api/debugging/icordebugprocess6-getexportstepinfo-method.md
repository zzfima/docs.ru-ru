---
title: Метод ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: d92b05e3d84a230e87901378f34ed27ac38286b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123462"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="67f01-102">Метод ICorDebugProcess6::GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="67f01-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="67f01-103">Предоставляет информацию о функциях, экспортируемых в ходе выполнения, для пошагового перемещения по управляемому коду.</span><span class="sxs-lookup"><span data-stu-id="67f01-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67f01-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67f01-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67f01-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="67f01-105">Parameters</span></span>  
 <span data-ttu-id="67f01-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="67f01-106">pszExportName</span></span>  
 <span data-ttu-id="67f01-107">[входной] Имя функции экспорта во время выполнения, записываемой в таблице экспорта PE.</span><span class="sxs-lookup"><span data-stu-id="67f01-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="67f01-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="67f01-108">invokeKind</span></span>  
 <span data-ttu-id="67f01-109">заполняет Указатель на член перечисления [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) , описывающий, как экспортируемая функция будет вызывать управляемый код.</span><span class="sxs-lookup"><span data-stu-id="67f01-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="67f01-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="67f01-110">invokePurpose</span></span>  
 <span data-ttu-id="67f01-111">заполняет Указатель на член перечисления [кордебугкодеинвокепурпосе](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) , описывающий, почему экспортируемая функция будет вызывать управляемый код.</span><span class="sxs-lookup"><span data-stu-id="67f01-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67f01-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="67f01-112">Return Value</span></span>  
 <span data-ttu-id="67f01-113">Метод может возвращать значения, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="67f01-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="67f01-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="67f01-114">Return value</span></span>|<span data-ttu-id="67f01-115">Описание</span><span class="sxs-lookup"><span data-stu-id="67f01-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="67f01-116">Успешный вызов метода.</span><span class="sxs-lookup"><span data-stu-id="67f01-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="67f01-117">`pInvokeKind` или `pInvokePurpose` имеет **значение NULL**.</span><span class="sxs-lookup"><span data-stu-id="67f01-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="67f01-118">Другие ошибочные значения `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="67f01-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="67f01-119">По мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="67f01-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67f01-120">Заметки</span><span class="sxs-lookup"><span data-stu-id="67f01-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67f01-121">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="67f01-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67f01-122">Требования</span><span class="sxs-lookup"><span data-stu-id="67f01-122">Requirements</span></span>  
 <span data-ttu-id="67f01-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67f01-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67f01-124">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67f01-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67f01-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67f01-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67f01-126">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67f01-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67f01-127">См. также</span><span class="sxs-lookup"><span data-stu-id="67f01-127">See also</span></span>

- [<span data-ttu-id="67f01-128">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="67f01-128">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="67f01-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="67f01-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
