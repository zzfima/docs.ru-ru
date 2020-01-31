---
title: Метод ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 969cca6d5613670fc4b26fc973785b4874c3684c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778074"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="3f6f9-102">Метод ICorDebugAssembly3::GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="3f6f9-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="3f6f9-103">Возвращает контейнерную сборку этого объекта `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="3f6f9-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f6f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f6f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f6f9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3f6f9-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="3f6f9-106">Указатель на адрес объекта ICorDebugAssembly, который представляет сборку контейнера, или **значение NULL** , если вызов метода завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3f6f9-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f6f9-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3f6f9-107">Return Value</span></span>  
 <span data-ttu-id="3f6f9-108">`S_OK`, если вызов метода выполнен. в противном случае `S_FALSE`и `ppAssembly` имеют **значение NULL**.</span><span class="sxs-lookup"><span data-stu-id="3f6f9-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f6f9-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="3f6f9-109">Remarks</span></span>  
 <span data-ttu-id="3f6f9-110">Если эта сборка была объединена с другими сборками внутри одиночной контейнерной сборки, этот метод возвращает контейнерную сборку.</span><span class="sxs-lookup"><span data-stu-id="3f6f9-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="3f6f9-111">Дополнительные сведения и терминология см. в разделе [ICorDebugProcess6:: EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3f6f9-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f6f9-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="3f6f9-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f6f9-113">Требования</span><span class="sxs-lookup"><span data-stu-id="3f6f9-113">Requirements</span></span>  
 <span data-ttu-id="3f6f9-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f6f9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f6f9-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f6f9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f6f9-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f6f9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f6f9-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f6f9-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f6f9-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="3f6f9-118">See also</span></span>

- [<span data-ttu-id="3f6f9-119">Интерфейс ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="3f6f9-119">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="3f6f9-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3f6f9-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
