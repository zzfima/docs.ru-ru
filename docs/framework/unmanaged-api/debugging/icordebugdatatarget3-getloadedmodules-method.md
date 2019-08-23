---
title: Метод ICorDebugDataTarget3::GetLoadedModules
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 120b839b2b11c85f42bb1a0ae4701de0dea33879
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912826"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="57d6a-102">Метод ICorDebugDataTarget3::GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="57d6a-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="57d6a-103">Возвращает список модулей, загруженных на данный момент.</span><span class="sxs-lookup"><span data-stu-id="57d6a-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57d6a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57d6a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57d6a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="57d6a-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="57d6a-106">[in] Число модулей, для которых запрашиваются сведения.</span><span class="sxs-lookup"><span data-stu-id="57d6a-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="57d6a-107">[out] Указатель на число модулей, о которых возвращаются сведения.</span><span class="sxs-lookup"><span data-stu-id="57d6a-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="57d6a-108">заполняет Указатель на массив объектов [икордебуглоадедмодуле](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) , которые предоставляют сведения о загруженных модулях.</span><span class="sxs-lookup"><span data-stu-id="57d6a-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57d6a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="57d6a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57d6a-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="57d6a-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57d6a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="57d6a-111">Requirements</span></span>  
 <span data-ttu-id="57d6a-112">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57d6a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57d6a-113">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="57d6a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57d6a-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="57d6a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57d6a-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57d6a-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57d6a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="57d6a-116">See also</span></span>

- [<span data-ttu-id="57d6a-117">Интерфейс ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="57d6a-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)
- [<span data-ttu-id="57d6a-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="57d6a-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
