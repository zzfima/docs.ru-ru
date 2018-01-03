---
title: "Метод ICorDebugAssembly3::EnumerateContainedAssemblies"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8633ce497cd282303c46692a942fe5f88be444c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="8f34a-102">Метод ICorDebugAssembly3::EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="8f34a-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="8f34a-103">Получает перечислитель для сборок, содержащихся в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="8f34a-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f34a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f34a-104">Syntax</span></span>  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f34a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8f34a-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="8f34a-106">[out] Указатель на адрес объекта интерфейса ICorDebugAssemblyEnum, который является перечислителем.</span><span class="sxs-lookup"><span data-stu-id="8f34a-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f34a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8f34a-107">Return Value</span></span>  
 <span data-ttu-id="8f34a-108">`S_OK`, если этот объект `ICorDebugAssembly3` является контейнером; в противном случае — `S_FALSE`, и перечисление будет пустым.</span><span class="sxs-lookup"><span data-stu-id="8f34a-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f34a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="8f34a-109">Remarks</span></span>  
 <span data-ttu-id="8f34a-110">Символы необходимы для перечисления вложенных сборок.</span><span class="sxs-lookup"><span data-stu-id="8f34a-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="8f34a-111">Если они отсутствуют, метод возвращает `S_FALSE`, и действительный перечислитель отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8f34a-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f34a-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="8f34a-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f34a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="8f34a-113">Requirements</span></span>  
 <span data-ttu-id="8f34a-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f34a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f34a-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f34a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f34a-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f34a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f34a-117">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f34a-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f34a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="8f34a-118">See Also</span></span>  
 [<span data-ttu-id="8f34a-119">Интерфейс ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="8f34a-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 [<span data-ttu-id="8f34a-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8f34a-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
