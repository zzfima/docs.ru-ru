---
title: Интерфейс ICorDebugGuidToTypeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2ea67c6e4d860d41cfe67aaab73babb51f3ce45
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210663"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="bbaa6-102">Интерфейс ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="bbaa6-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="bbaa6-103">Предоставляет перечислитель, который определяет сопоставление между набором идентификаторов GUID и соответствующие им типы, которые представлены экземплярами ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="bbaa6-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="bbaa6-104">Этот интерфейс наследует интерфейс ICorDebugEnum методы.</span><span class="sxs-lookup"><span data-stu-id="bbaa6-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bbaa6-105">Методы</span><span class="sxs-lookup"><span data-stu-id="bbaa6-105">Methods</span></span>  
  
|<span data-ttu-id="bbaa6-106">Метод</span><span class="sxs-lookup"><span data-stu-id="bbaa6-106">Method</span></span>|<span data-ttu-id="bbaa6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bbaa6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bbaa6-108">ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="bbaa6-108">ICorDebugGuidToTypeEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="bbaa6-109">Возвращает заданное число [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) экземпляров, которые сопоставляют идентификаторов GUID, чтобы сведения о типе.</span><span class="sxs-lookup"><span data-stu-id="bbaa6-109">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbaa6-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="bbaa6-110">Remarks</span></span>  
 <span data-ttu-id="bbaa6-111">`ICorDebugGuidToTypeEnum` Объект интерфейса можно получить, вызвав [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="bbaa6-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="bbaa6-112">Отладчик может вызвать этот интерфейс [Далее](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) метод для извлечения [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) представлений управляемых объектов, представляющих сопоставления [!INCLUDE[wrt](../../../../includes/wrt-md.md)] загрузке типов в домен приложения и используется для вызова [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="bbaa6-112">A debugger can call this interface's [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbaa6-113">Требования</span><span class="sxs-lookup"><span data-stu-id="bbaa6-113">Requirements</span></span>  
 **<span data-ttu-id="bbaa6-114">Платформы:</span><span class="sxs-lookup"><span data-stu-id="bbaa6-114">Platforms:</span></span>** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 <span data-ttu-id="bbaa6-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bbaa6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bbaa6-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbaa6-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bbaa6-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bbaa6-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bbaa6-118">См. также</span><span class="sxs-lookup"><span data-stu-id="bbaa6-118">See also</span></span>

- [<span data-ttu-id="bbaa6-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bbaa6-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
