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
ms.openlocfilehash: da921644c4d967efb0d88060ada0332c5eb63965
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138534"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="b8013-102">Интерфейс ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="b8013-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="b8013-103">Предоставляет перечислитель, который определяет сопоставление между набором идентификаторов GUID и соответствующими типами, которые представлены экземплярами ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="b8013-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="b8013-104">Этот интерфейс наследует методы от интерфейса ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="b8013-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8013-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b8013-105">Methods</span></span>  
  
|<span data-ttu-id="b8013-106">Метод</span><span class="sxs-lookup"><span data-stu-id="b8013-106">Method</span></span>|<span data-ttu-id="b8013-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b8013-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8013-108">ICorDebugGuidToTypeEnum:: Next</span><span class="sxs-lookup"><span data-stu-id="b8013-108">ICorDebugGuidToTypeEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="b8013-109">Возвращает указанное число экземпляров [кордебуггуидтотипемаппинг](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) , которые сопоставляют идентификаторы GUID со сведениями о типе.</span><span class="sxs-lookup"><span data-stu-id="b8013-109">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8013-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="b8013-110">Remarks</span></span>  
 <span data-ttu-id="b8013-111">Объект интерфейса `ICorDebugGuidToTypeEnum` можно извлечь, вызвав метод [ICorDebugAppDomain3:: GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b8013-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="b8013-112">Отладчик может вызвать [следующий](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) метод этого интерфейса для получения объектов [кордебуггуидтотипемаппинг](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) , представляющих сопоставления управляемых представлений типов Среда выполнения Windows, загруженных в домен приложения, используемый для вызова метода [ Метод ICorDebugAppDomain3:: GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b8013-112">A debugger can call this interface's [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of Windows Runtime types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8013-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b8013-113">Requirements</span></span>  
 <span data-ttu-id="b8013-114">**Платформы:** среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="b8013-114">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="b8013-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8013-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8013-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8013-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8013-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8013-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8013-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b8013-118">See also</span></span>

- [<span data-ttu-id="b8013-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b8013-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
