---
title: Метод ICorDebugProcess5::GetTypeLayout
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
ms.openlocfilehash: a348c3b2ad33a5d68b1bc46e9a284f2d2a9c7304
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121287"
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="bb486-102">Метод ICorDebugProcess5::GetTypeLayout</span><span class="sxs-lookup"><span data-stu-id="bb486-102">ICorDebugProcess5::GetTypeLayout Method</span></span>
<span data-ttu-id="bb486-103">Возвращает сведения о макете объекта в памяти на основе его идентификатора типа.</span><span class="sxs-lookup"><span data-stu-id="bb486-103">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb486-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb486-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb486-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb486-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="bb486-106">окне Токен [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) , указывающий тип, макет которого требуется.</span><span class="sxs-lookup"><span data-stu-id="bb486-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="bb486-107">заполняет Указатель на структуру [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) , содержащую сведения о макете объекта в памяти.</span><span class="sxs-lookup"><span data-stu-id="bb486-107">[out] A pointer to a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb486-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="bb486-108">Remarks</span></span>  
 <span data-ttu-id="bb486-109">Метод `ICorDebugProcess5::GetTypeLayout` предоставляет сведения об объекте на основе его [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), который возвращается несколькими другими методами [метод ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="bb486-109">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="bb486-110">Сведения предоставляются структурой [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) , заполняемой методом.</span><span class="sxs-lookup"><span data-stu-id="bb486-110">The information is provided by a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb486-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bb486-111">Requirements</span></span>  
 <span data-ttu-id="bb486-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb486-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb486-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb486-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb486-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb486-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb486-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb486-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb486-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bb486-116">See also</span></span>

- [<span data-ttu-id="bb486-117">Структура COR_TYPE_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="bb486-117">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)
- [<span data-ttu-id="bb486-118">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="bb486-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="bb486-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bb486-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
