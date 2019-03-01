---
title: Интерфейс ICorDebugClass
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9beb8930143cbb0cc7dd8dd68a65b42d92563e31
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972057"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="fa3af-102">Интерфейс ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="fa3af-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="fa3af-103">Представляет тип, который может быть базовым или сложным (иными словами, пользовательским).</span><span class="sxs-lookup"><span data-stu-id="fa3af-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="fa3af-104">Если тип универсальный, `ICorDebugClass` представляет универсальный тип, у которого отсутствуют экземпляры.</span><span class="sxs-lookup"><span data-stu-id="fa3af-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa3af-105">Методы</span><span class="sxs-lookup"><span data-stu-id="fa3af-105">Methods</span></span>  
  
|<span data-ttu-id="fa3af-106">Метод</span><span class="sxs-lookup"><span data-stu-id="fa3af-106">Method</span></span>|<span data-ttu-id="fa3af-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="fa3af-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa3af-108">Метод GetModule</span><span class="sxs-lookup"><span data-stu-id="fa3af-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="fa3af-109">Возвращает модуль, в котором определен этот класс.</span><span class="sxs-lookup"><span data-stu-id="fa3af-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="fa3af-110">Метод GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="fa3af-110">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="fa3af-111">Получает значение указанного статического поля.</span><span class="sxs-lookup"><span data-stu-id="fa3af-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="fa3af-112">Метод GetToken</span><span class="sxs-lookup"><span data-stu-id="fa3af-112">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|<span data-ttu-id="fa3af-113">Получает `TypeDef` маркер метаданных для данного класса.</span><span class="sxs-lookup"><span data-stu-id="fa3af-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa3af-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="fa3af-114">Remarks</span></span>  
 <span data-ttu-id="fa3af-115">`ICorDebugClass` Интерфейс представляет универсального типа без экземпляров.</span><span class="sxs-lookup"><span data-stu-id="fa3af-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="fa3af-116">Интерфейс ICorDebugType представляет экземпляры универсального типа.</span><span class="sxs-lookup"><span data-stu-id="fa3af-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="fa3af-117">Например `Hashtable<K, V>` будут представлены в `ICorDebugClass`, тогда как `Hashtable<Int32, String>` будут представлены в `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="fa3af-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="fa3af-118">Неуниверсальные типы представлены оба `ICorDebugClass` и `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="fa3af-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="fa3af-119">Последний интерфейс появился в .NET Framework версии 2.0 для создания экземпляров типов.</span><span class="sxs-lookup"><span data-stu-id="fa3af-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa3af-120">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="fa3af-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa3af-121">Требования</span><span class="sxs-lookup"><span data-stu-id="fa3af-121">Requirements</span></span>  
 <span data-ttu-id="fa3af-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa3af-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa3af-123">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa3af-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa3af-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa3af-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa3af-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa3af-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa3af-126">См. также</span><span class="sxs-lookup"><span data-stu-id="fa3af-126">See also</span></span>
- [<span data-ttu-id="fa3af-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fa3af-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
