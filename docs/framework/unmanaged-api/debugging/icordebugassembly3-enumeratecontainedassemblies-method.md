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
ms.openlocfilehash: b927d065f26a13d496aec8cd6c8cbc69cf3a8bc9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="54114-102">Метод ICorDebugAssembly3::EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="54114-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="54114-103">Получает перечислитель для сборок, содержащихся в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="54114-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54114-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54114-104">Syntax</span></span>  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54114-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="54114-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="54114-106">[out] Указатель на адрес объекта интерфейса ICorDebugAssemblyEnum, который является перечислителем.</span><span class="sxs-lookup"><span data-stu-id="54114-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54114-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="54114-107">Return Value</span></span>  
 <span data-ttu-id="54114-108">`S_OK`, если этот объект `ICorDebugAssembly3` является контейнером; в противном случае — `S_FALSE`, и перечисление будет пустым.</span><span class="sxs-lookup"><span data-stu-id="54114-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54114-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="54114-109">Remarks</span></span>  
 <span data-ttu-id="54114-110">Символы необходимы для перечисления вложенных сборок.</span><span class="sxs-lookup"><span data-stu-id="54114-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="54114-111">Если они отсутствуют, метод возвращает `S_FALSE`, и действительный перечислитель отсутствует.</span><span class="sxs-lookup"><span data-stu-id="54114-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54114-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="54114-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54114-113">Требования</span><span class="sxs-lookup"><span data-stu-id="54114-113">Requirements</span></span>  
 <span data-ttu-id="54114-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54114-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54114-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54114-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54114-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54114-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54114-117">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54114-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54114-118">См. также</span><span class="sxs-lookup"><span data-stu-id="54114-118">See Also</span></span>  
 [<span data-ttu-id="54114-119">Интерфейс ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="54114-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 [<span data-ttu-id="54114-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="54114-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
