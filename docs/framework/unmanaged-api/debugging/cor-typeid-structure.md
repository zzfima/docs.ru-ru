---
title: Структура COR_TYPEID
ms.date: 03/30/2017
api_name:
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d76fa4b2352da18b5ef0e547ebc4e2e99d980b8
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71273998"
---
# <a name="cor_typeid-structure"></a><span data-ttu-id="e219f-102">Структура COR_TYPEID</span><span class="sxs-lookup"><span data-stu-id="e219f-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="e219f-103">Содержит идентификатор типа.</span><span class="sxs-lookup"><span data-stu-id="e219f-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e219f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e219f-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="e219f-105">Участники</span><span class="sxs-lookup"><span data-stu-id="e219f-105">Members</span></span>  
  
|<span data-ttu-id="e219f-106">Член</span><span class="sxs-lookup"><span data-stu-id="e219f-106">Member</span></span>|<span data-ttu-id="e219f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e219f-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="e219f-108">Первый токен.</span><span class="sxs-lookup"><span data-stu-id="e219f-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="e219f-109">Второй токен.</span><span class="sxs-lookup"><span data-stu-id="e219f-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e219f-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="e219f-110">Remarks</span></span>  
 <span data-ttu-id="e219f-111">`COR_TYPEID` Структура возвращается несколькими методами отладки, которые предоставляют сведения об объектах, которые должны быть собраны в мусор.</span><span class="sxs-lookup"><span data-stu-id="e219f-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="e219f-112">Затем его можно передать в качестве аргумента другим методам отладки, которые предоставляют дополнительные сведения об этом элементе.</span><span class="sxs-lookup"><span data-stu-id="e219f-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="e219f-113">Например, при перечислении объекта [икордебугхеапенум](icordebugheapenum-interface.md) можно получить отдельные объекты [COR_HEAPOBJECT](cor-heapobject-structure.md) , представляющие отдельные объекты в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="e219f-113">For example, by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="e219f-114">Затем можно передать `COR_TYPEID` значение `COR_HEAPOBJECT.type` из поля в метод [метод ICorDebugProcess5:: жеттипефортипеид](icordebugprocess5-gettypefortypeid-method.md) , чтобы получить объект ICorDebugType, предоставляющий сведения о типе объекта.</span><span class="sxs-lookup"><span data-stu-id="e219f-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="e219f-115">`COR_TYPEID` Объект должен быть непрозрачным.</span><span class="sxs-lookup"><span data-stu-id="e219f-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="e219f-116">Доступ к отдельным полям не должен осуществляться или манипулировать им.</span><span class="sxs-lookup"><span data-stu-id="e219f-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="e219f-117">Его единственное использование — это идентификатор, предоставляемый как `out` параметр в вызове метода, который, в свою очередь, может быть передан другим методам для предоставления дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="e219f-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e219f-118">Требования</span><span class="sxs-lookup"><span data-stu-id="e219f-118">Requirements</span></span>  
 <span data-ttu-id="e219f-119">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e219f-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e219f-120">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="e219f-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e219f-121">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="e219f-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e219f-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e219f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e219f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e219f-123">See also</span></span>

- [<span data-ttu-id="e219f-124">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="e219f-124">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="e219f-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="e219f-125">Debugging</span></span>](index.md)
