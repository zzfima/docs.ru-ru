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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16da3948d89febc12a72ef54fbc060689a3964c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423251"
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="c22bf-102">Метод ICorDebugProcess5::GetTypeLayout</span><span class="sxs-lookup"><span data-stu-id="c22bf-102">ICorDebugProcess5::GetTypeLayout Method</span></span>
<span data-ttu-id="c22bf-103">Возвращает сведения о расположении объекта в памяти в зависимости от его типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="c22bf-103">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c22bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c22bf-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c22bf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c22bf-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="c22bf-106">[in] Объект [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) маркер, который задает тип требуемого, макет.</span><span class="sxs-lookup"><span data-stu-id="c22bf-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="c22bf-107">[out] Указатель на [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) структуру, содержащую сведения о расположении объекта в памяти.</span><span class="sxs-lookup"><span data-stu-id="c22bf-107">[out] A pointer to a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c22bf-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c22bf-108">Remarks</span></span>  
 <span data-ttu-id="c22bf-109">`ICorDebugProcess5::GetTypeLayout` Метод предоставляет сведения об объекте на основе его [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), который возвращается количество других [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) методы.</span><span class="sxs-lookup"><span data-stu-id="c22bf-109">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="c22bf-110">Предоставляемые сведения [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) структуру, которая заполняется с помощью метода.</span><span class="sxs-lookup"><span data-stu-id="c22bf-110">The information is provided by a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c22bf-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c22bf-111">Requirements</span></span>  
 <span data-ttu-id="c22bf-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c22bf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c22bf-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c22bf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c22bf-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c22bf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c22bf-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c22bf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c22bf-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c22bf-116">See Also</span></span>  
 [<span data-ttu-id="c22bf-117">Структура COR_TYPE_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="c22bf-117">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 [<span data-ttu-id="c22bf-118">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="c22bf-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="c22bf-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c22bf-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
