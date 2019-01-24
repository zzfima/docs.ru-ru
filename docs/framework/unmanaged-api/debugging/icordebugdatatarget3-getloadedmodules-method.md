---
title: Метод ICorDebugDataTarget3::GetLoadedModules
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b961e0a84d199f0acf22dfc0f87b1d35c118adc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651062"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="e1e15-102">Метод ICorDebugDataTarget3::GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="e1e15-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="e1e15-103">Возвращает список модулей, загруженных в данный момент.</span><span class="sxs-lookup"><span data-stu-id="e1e15-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1e15-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1e15-104">Syntax</span></span>  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1e15-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1e15-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="e1e15-106">[in] Число модулей, для которых запрашиваются сведения.</span><span class="sxs-lookup"><span data-stu-id="e1e15-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="e1e15-107">[out] Указатель на число модулей, о которых возвращаются сведения.</span><span class="sxs-lookup"><span data-stu-id="e1e15-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="e1e15-108">[out] Указатель на массив [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) объектов, которые предоставляют сведения о загруженных модулей.</span><span class="sxs-lookup"><span data-stu-id="e1e15-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1e15-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="e1e15-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1e15-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="e1e15-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1e15-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e1e15-111">Requirements</span></span>  
 <span data-ttu-id="e1e15-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1e15-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1e15-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1e15-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1e15-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1e15-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1e15-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1e15-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e15-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e1e15-116">See also</span></span>
- [<span data-ttu-id="e1e15-117">Интерфейс ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="e1e15-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)
- [<span data-ttu-id="e1e15-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e1e15-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
