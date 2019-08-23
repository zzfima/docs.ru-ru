---
title: Метод ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9120119056fda3f16b4a0bf8bad839b74463d633
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959332"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="155ff-102">Метод ICorDebugAssembly3::EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="155ff-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="155ff-103">Получает перечислитель для сборок, содержащихся в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="155ff-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="155ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="155ff-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="155ff-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="155ff-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="155ff-106">заполняет Указатель на адрес объекта интерфейса ICorDebugAssemblyEnum, который является перечислителем.</span><span class="sxs-lookup"><span data-stu-id="155ff-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="155ff-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="155ff-107">Return Value</span></span>  
 <span data-ttu-id="155ff-108">`S_OK`, если этот объект `ICorDebugAssembly3` является контейнером; в противном случае — `S_FALSE`, и перечисление будет пустым.</span><span class="sxs-lookup"><span data-stu-id="155ff-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="155ff-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="155ff-109">Remarks</span></span>  
 <span data-ttu-id="155ff-110">Символы необходимы для перечисления вложенных сборок.</span><span class="sxs-lookup"><span data-stu-id="155ff-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="155ff-111">Если они отсутствуют, метод возвращает `S_FALSE`, и действительный перечислитель отсутствует.</span><span class="sxs-lookup"><span data-stu-id="155ff-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="155ff-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="155ff-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="155ff-113">Требования</span><span class="sxs-lookup"><span data-stu-id="155ff-113">Requirements</span></span>  
 <span data-ttu-id="155ff-114">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="155ff-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="155ff-115">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="155ff-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="155ff-116">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="155ff-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="155ff-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="155ff-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="155ff-118">См. также</span><span class="sxs-lookup"><span data-stu-id="155ff-118">See also</span></span>

- [<span data-ttu-id="155ff-119">Интерфейс ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="155ff-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="155ff-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="155ff-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
