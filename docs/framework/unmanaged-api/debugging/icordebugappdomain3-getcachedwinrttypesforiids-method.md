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
ms.openlocfilehash: 0369cc6d98736542b764e5914d733a9341753b24
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088880"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="1751c-102">Метод ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="1751c-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="1751c-103">Возвращает перечислитель для кэшированных среда выполнения Windowsных типов в домене приложения на основе их идентификаторов интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="1751c-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1751c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1751c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1751c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1751c-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="1751c-106">окне Число обязательных типов.</span><span class="sxs-lookup"><span data-stu-id="1751c-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="1751c-107">окне Указатель на массив, содержащий идентификаторы интерфейса, соответствующие управляемым представлениям возвращаемых типов среда выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="1751c-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="1751c-108">заполняет Указатель на адрес объекта "ICorDebugTypeEnum" интерфейса, который позволяет перечислить кэшированные управляемые представления возвращаемых типов среда выполнения Windows на основе идентификаторов интерфейса в `iidsToResolve`.</span><span class="sxs-lookup"><span data-stu-id="1751c-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1751c-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="1751c-109">Remarks</span></span>  
 <span data-ttu-id="1751c-110">Если методу не удается получить сведения для определенного идентификатора интерфейса, соответствующая запись в коллекции "ICorDebugTypeEnum" будет иметь тип `ELEMENT_TYPE_END` для ошибок из-за проблем, связанных с получением данных, или `ELEMENT_TYPE_VOID` для неизвестных идентификаторов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1751c-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1751c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1751c-111">Requirements</span></span>  
 <span data-ttu-id="1751c-112">**Платформы:** среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="1751c-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="1751c-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1751c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1751c-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1751c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1751c-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1751c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1751c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1751c-116">See also</span></span>

- [<span data-ttu-id="1751c-117">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="1751c-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
