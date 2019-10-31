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
ms.openlocfilehash: 4f6dbe8c17bd6a91078b87a87c1055fbf4977a88
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132300"
---
# <a name="cor_typeid-structure"></a><span data-ttu-id="711d7-102">Структура COR_TYPEID</span><span class="sxs-lookup"><span data-stu-id="711d7-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="711d7-103">Содержит идентификатор типа.</span><span class="sxs-lookup"><span data-stu-id="711d7-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="711d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="711d7-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="711d7-105">Члены</span><span class="sxs-lookup"><span data-stu-id="711d7-105">Members</span></span>  
  
|<span data-ttu-id="711d7-106">Член</span><span class="sxs-lookup"><span data-stu-id="711d7-106">Member</span></span>|<span data-ttu-id="711d7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="711d7-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="711d7-108">Первый токен.</span><span class="sxs-lookup"><span data-stu-id="711d7-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="711d7-109">Второй токен.</span><span class="sxs-lookup"><span data-stu-id="711d7-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="711d7-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="711d7-110">Remarks</span></span>  
 <span data-ttu-id="711d7-111">Структура `COR_TYPEID` возвращается несколькими методами отладки, которые предоставляют сведения об объектах, которые должны быть собраны в мусор.</span><span class="sxs-lookup"><span data-stu-id="711d7-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="711d7-112">Затем его можно передать в качестве аргумента другим методам отладки, которые предоставляют дополнительные сведения об этом элементе.</span><span class="sxs-lookup"><span data-stu-id="711d7-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="711d7-113">Например, при перечислении объекта [икордебугхеапенум](icordebugheapenum-interface.md) можно получить отдельные объекты [COR_HEAPOBJECT](cor-heapobject-structure.md) , представляющие отдельные объекты в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="711d7-113">For example, by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="711d7-114">Затем можно передать значение `COR_TYPEID` из поля `COR_HEAPOBJECT.type` в метод [метод ICorDebugProcess5:: жеттипефортипеид](icordebugprocess5-gettypefortypeid-method.md) , чтобы получить объект ICorDebugType, предоставляющий сведения о типе объекта.</span><span class="sxs-lookup"><span data-stu-id="711d7-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="711d7-115">Объект `COR_TYPEID` должен быть непрозрачным.</span><span class="sxs-lookup"><span data-stu-id="711d7-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="711d7-116">Доступ к отдельным полям не должен осуществляться или манипулировать им.</span><span class="sxs-lookup"><span data-stu-id="711d7-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="711d7-117">Его единственное использование — это идентификатор, который предоставляется как параметр `out` в вызове метода, который, в свою очередь, может быть передан другим методам для предоставления дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="711d7-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="711d7-118">Требования</span><span class="sxs-lookup"><span data-stu-id="711d7-118">Requirements</span></span>  
 <span data-ttu-id="711d7-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="711d7-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="711d7-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="711d7-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="711d7-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="711d7-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="711d7-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="711d7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="711d7-123">См. также</span><span class="sxs-lookup"><span data-stu-id="711d7-123">See also</span></span>

- [<span data-ttu-id="711d7-124">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="711d7-124">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="711d7-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="711d7-125">Debugging</span></span>](index.md)
