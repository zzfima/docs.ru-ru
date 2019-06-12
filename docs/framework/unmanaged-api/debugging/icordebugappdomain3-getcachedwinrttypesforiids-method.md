---
title: Метод ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95c84f7f40db0096b26ec448f8f229cdbfe3afb1
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025904"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="cccdd-102">Метод ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="cccdd-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="cccdd-103">Возвращает перечислитель для кэшированных типов среды выполнения Windows в домене приложения, на основе их идентификаторов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="cccdd-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cccdd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cccdd-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cccdd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cccdd-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="cccdd-106">[in] Количество требуемых типов.</span><span class="sxs-lookup"><span data-stu-id="cccdd-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="cccdd-107">[in] Указатель на массив, содержащий идентификаторы интерфейса, соответствующие управляемые представления типов среды выполнения Windows требуется получить.</span><span class="sxs-lookup"><span data-stu-id="cccdd-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="cccdd-108">[out] Получить указатель на адрес объекта интерфейса «ICorDebugTypeEnum», который позволяет использовать перечисления кэшированного представления управляемых типов среды выполнения Windows, на основе идентификаторов интерфейса в `iidsToResolve`.</span><span class="sxs-lookup"><span data-stu-id="cccdd-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cccdd-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="cccdd-109">Remarks</span></span>  
 <span data-ttu-id="cccdd-110">При сбое метода для получения сведений для определенного интерфейса идентификатора, соответствующая запись в коллекции «ICorDebugTypeEnum» будет иметь тип `ELEMENT_TYPE_END` ошибок из-за проблем извлечения данных, или `ELEMENT_TYPE_VOID` для Неизвестный интерфейс идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="cccdd-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cccdd-111">Требования</span><span class="sxs-lookup"><span data-stu-id="cccdd-111">Requirements</span></span>  
 <span data-ttu-id="cccdd-112">**Платформы:** Среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="cccdd-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="cccdd-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cccdd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cccdd-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cccdd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cccdd-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cccdd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cccdd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="cccdd-116">See also</span></span>

- [<span data-ttu-id="cccdd-117">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="cccdd-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
