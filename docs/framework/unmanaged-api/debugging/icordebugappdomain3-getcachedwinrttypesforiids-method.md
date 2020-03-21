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
ms.openlocfilehash: f8e92ec4f813e8810273a1514298d0739a3d2406
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179062"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="57b8f-102">Метод ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="57b8f-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="57b8f-103">Получает регистратор для кэшированных типов Windows Runtime в домене приложения на основе идентификаторов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="57b8f-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57b8f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57b8f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57b8f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="57b8f-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="57b8f-106">(в) Количество требуемых типов.</span><span class="sxs-lookup"><span data-stu-id="57b8f-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="57b8f-107">(в) Указатель массива, содержащего идентификаторы интерфейса, соответствующие управляемым представлениям типов Windows Runtime, которые должны быть извлечены.</span><span class="sxs-lookup"><span data-stu-id="57b8f-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="57b8f-108">(ваут) Указатель на адрес объекта интерфейса "ICorDebugTypeEnum", позволяющий перечислять извлеченные кэшированные управляемые представления извлеченных типов Windows `iidsToResolve`Runtime на основе идентификаторов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="57b8f-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57b8f-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="57b8f-109">Remarks</span></span>  
 <span data-ttu-id="57b8f-110">Если метод не может получить информацию для конкретного идентификатора интерфейса, соответствующая запись в `ELEMENT_TYPE_END` коллекции "ICorDebugTypeEnum" будет иметь тип для ошибок из-за проблем с поиском данных или `ELEMENT_TYPE_VOID` для неизвестных идентификаторов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="57b8f-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57b8f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="57b8f-111">Requirements</span></span>  
 <span data-ttu-id="57b8f-112">**Платформы:** Время выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="57b8f-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="57b8f-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57b8f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57b8f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57b8f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57b8f-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57b8f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57b8f-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="57b8f-116">See also</span></span>

- [<span data-ttu-id="57b8f-117">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="57b8f-117">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
