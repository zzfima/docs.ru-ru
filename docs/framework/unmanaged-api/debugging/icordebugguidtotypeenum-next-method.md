---
title: Метод ICorDebugGuidToTypeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
ms.openlocfilehash: f6f190cd5b2f208df5a4ed88b650af671f2e6c5c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138519"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="08c2e-102">Метод ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="08c2e-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="08c2e-103">Возвращает указанное число экземпляров [кордебуггуидтотипемаппинг](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) , которые сопоставляют идентификаторы GUID со сведениями о типе.</span><span class="sxs-lookup"><span data-stu-id="08c2e-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08c2e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08c2e-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08c2e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="08c2e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="08c2e-106">окне Число получаемых объектов сопоставления GUID и типа.</span><span class="sxs-lookup"><span data-stu-id="08c2e-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="08c2e-107">заполняет Массив указателей, каждый из которых указывает на объект [кордебуггуидтотипемаппинг](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) , который сопоставляет идентификатор GUID среда выполнения Windows с соответствующим объектом ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="08c2e-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="08c2e-108">заполняет Указатель на число объектов [кордебуггуидтотипемаппинг](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) , фактически возвращаемых в `values`.</span><span class="sxs-lookup"><span data-stu-id="08c2e-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08c2e-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="08c2e-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08c2e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="08c2e-110">Requirements</span></span>  
 <span data-ttu-id="08c2e-111">**Платформы:** среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="08c2e-111">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="08c2e-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08c2e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08c2e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08c2e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08c2e-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08c2e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c2e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="08c2e-115">See also</span></span>

- [<span data-ttu-id="08c2e-116">Интерфейс ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="08c2e-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="08c2e-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="08c2e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
