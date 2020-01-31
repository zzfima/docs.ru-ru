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
ms.openlocfilehash: 8b259636a8bd28abd3bba12c4a05dda3c13557e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784894"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="11a72-102">Метод ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="11a72-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="11a72-103">Возвращает перечислитель для кэшированных среда выполнения Windowsных типов в домене приложения на основе их идентификаторов интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="11a72-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a72-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11a72-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11a72-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="11a72-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="11a72-106">окне Число обязательных типов.</span><span class="sxs-lookup"><span data-stu-id="11a72-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="11a72-107">окне Указатель на массив, содержащий идентификаторы интерфейса, соответствующие управляемым представлениям возвращаемых типов среда выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="11a72-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="11a72-108">заполняет Указатель на адрес объекта "ICorDebugTypeEnum" интерфейса, который позволяет перечислить кэшированные управляемые представления возвращаемых типов среда выполнения Windows на основе идентификаторов интерфейса в `iidsToResolve`.</span><span class="sxs-lookup"><span data-stu-id="11a72-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11a72-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="11a72-109">Remarks</span></span>  
 <span data-ttu-id="11a72-110">Если методу не удается получить сведения для определенного идентификатора интерфейса, соответствующая запись в коллекции "ICorDebugTypeEnum" будет иметь тип `ELEMENT_TYPE_END` для ошибок из-за проблем, связанных с получением данных, или `ELEMENT_TYPE_VOID` для неизвестных идентификаторов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="11a72-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11a72-111">Требования</span><span class="sxs-lookup"><span data-stu-id="11a72-111">Requirements</span></span>  
 <span data-ttu-id="11a72-112">**Платформы:** среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="11a72-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="11a72-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11a72-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11a72-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11a72-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11a72-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11a72-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a72-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="11a72-116">See also</span></span>

- [<span data-ttu-id="11a72-117">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="11a72-117">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
