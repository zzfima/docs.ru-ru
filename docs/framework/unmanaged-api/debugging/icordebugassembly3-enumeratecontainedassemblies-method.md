---
title: Метод ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1032227a539fb0f1a670a2c1a7a0f4f7df05a82b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466869"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="2d01c-102">Метод ICorDebugAssembly3::EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="2d01c-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="2d01c-103">Получает перечислитель для сборок, содержащихся в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="2d01c-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d01c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d01c-104">Syntax</span></span>  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d01c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2d01c-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="2d01c-106">[out] Указатель на адрес объекта интерфейса ICorDebugAssemblyEnum, который является перечислителем.</span><span class="sxs-lookup"><span data-stu-id="2d01c-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d01c-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2d01c-107">Return Value</span></span>  
 <span data-ttu-id="2d01c-108">`S_OK`, если этот объект `ICorDebugAssembly3` является контейнером; в противном случае — `S_FALSE`, и перечисление будет пустым.</span><span class="sxs-lookup"><span data-stu-id="2d01c-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d01c-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="2d01c-109">Remarks</span></span>  
 <span data-ttu-id="2d01c-110">Символы необходимы для перечисления вложенных сборок.</span><span class="sxs-lookup"><span data-stu-id="2d01c-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="2d01c-111">Если они отсутствуют, метод возвращает `S_FALSE`, и действительный перечислитель отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2d01c-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d01c-112">Этот метод доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2d01c-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d01c-113">Требования</span><span class="sxs-lookup"><span data-stu-id="2d01c-113">Requirements</span></span>  
 <span data-ttu-id="2d01c-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d01c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d01c-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d01c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d01c-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d01c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d01c-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d01c-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d01c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2d01c-118">See also</span></span>
- [<span data-ttu-id="2d01c-119">Интерфейс ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="2d01c-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="2d01c-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2d01c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
