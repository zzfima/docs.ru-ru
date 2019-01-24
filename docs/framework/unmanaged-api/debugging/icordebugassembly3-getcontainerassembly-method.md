---
title: Метод ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c01898bcbd76f7e6de9445d5d1f511203c100ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585189"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="8c238-102">Метод ICorDebugAssembly3::GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="8c238-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="8c238-103">Возвращает контейнерную сборку этого объекта `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="8c238-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c238-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c238-104">Syntax</span></span>  
  
```  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c238-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c238-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="8c238-106">Указатель на адрес ICorDebugAssembly объекта, представляющего контейнерную сборку, или **null** при сбое вызова метода.</span><span class="sxs-lookup"><span data-stu-id="8c238-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c238-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8c238-107">Return Value</span></span>  
 <span data-ttu-id="8c238-108">`S_OK` Если вызов метода выполнен успешно; в противном случае `S_FALSE`, и `ppAssembly` — **null**.</span><span class="sxs-lookup"><span data-stu-id="8c238-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c238-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c238-109">Remarks</span></span>  
 <span data-ttu-id="8c238-110">Если эта сборка была объединена с другими сборками внутри одиночной контейнерной сборки, этот метод возвращает контейнерную сборку.</span><span class="sxs-lookup"><span data-stu-id="8c238-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="8c238-111">Дополнительные сведения и терминологию см. в разделе [ICorDebugProcess6::EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="8c238-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c238-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="8c238-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c238-113">Требования</span><span class="sxs-lookup"><span data-stu-id="8c238-113">Requirements</span></span>  
 <span data-ttu-id="8c238-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c238-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c238-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c238-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c238-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c238-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c238-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c238-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c238-118">См. также</span><span class="sxs-lookup"><span data-stu-id="8c238-118">See also</span></span>
- [<span data-ttu-id="8c238-119">Интерфейс ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="8c238-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="8c238-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8c238-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
