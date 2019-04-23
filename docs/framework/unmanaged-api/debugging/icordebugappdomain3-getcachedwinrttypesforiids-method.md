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
ms.openlocfilehash: ed1d7ad95b7c8474121994d0f54557c1c36cb531
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59095130"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="0a3a7-102">Метод ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="0a3a7-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="0a3a7-103">Получает перечислитель для кэшированных [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типов в домене приложения, по их идентификаторам интерфейс.</span><span class="sxs-lookup"><span data-stu-id="0a3a7-103">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a3a7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a3a7-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a3a7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a3a7-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="0a3a7-106">[in] Количество требуемых типов.</span><span class="sxs-lookup"><span data-stu-id="0a3a7-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="0a3a7-107">[in] Указатель на массив, содержащий идентификаторы интерфейса, соответствующие управляемые представления [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типы должны быть получены.</span><span class="sxs-lookup"><span data-stu-id="0a3a7-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="0a3a7-108">[out] Указатель на адрес объекта интерфейса «ICorDebugTypeEnum», который позволяет использовать кэшированный перечисления управляемых представлений [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типы, полученные на основе идентификаторов интерфейса в `iidsToResolve`.</span><span class="sxs-lookup"><span data-stu-id="0a3a7-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a3a7-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="0a3a7-109">Remarks</span></span>  
 <span data-ttu-id="0a3a7-110">При сбое метода для получения сведений для определенного интерфейса идентификатора, соответствующая запись в коллекции «ICorDebugTypeEnum» будет иметь тип `ELEMENT_TYPE_END` ошибок из-за проблем извлечения данных, или `ELEMENT_TYPE_VOID` для Неизвестный интерфейс идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="0a3a7-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a3a7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0a3a7-111">Requirements</span></span>  
 <span data-ttu-id="0a3a7-112">**Платформы:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a3a7-112">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="0a3a7-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a3a7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a3a7-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a3a7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a3a7-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a3a7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a3a7-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0a3a7-116">See also</span></span>

- [<span data-ttu-id="0a3a7-117">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="0a3a7-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
