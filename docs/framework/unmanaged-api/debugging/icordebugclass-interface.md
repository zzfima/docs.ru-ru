---
title: ICorDebugClass интерфейс1
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
ms.openlocfilehash: bec35babec96da5ca5d527b19f853b4ce1c384e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406940"
---
# <a name="icordebugclass-interface1"></a><span data-ttu-id="fac11-102">ICorDebugClass интерфейс1</span><span class="sxs-lookup"><span data-stu-id="fac11-102">ICorDebugClass Interface1</span></span>
<span data-ttu-id="fac11-103">Представляет тип, который может быть базовым или сложным (иными словами, пользовательским).</span><span class="sxs-lookup"><span data-stu-id="fac11-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="fac11-104">Если тип универсальный, `ICorDebugClass` представляет универсальный тип, у которого отсутствуют экземпляры.</span><span class="sxs-lookup"><span data-stu-id="fac11-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fac11-105">Методы</span><span class="sxs-lookup"><span data-stu-id="fac11-105">Methods</span></span>  
  
|<span data-ttu-id="fac11-106">Метод</span><span class="sxs-lookup"><span data-stu-id="fac11-106">Method</span></span>|<span data-ttu-id="fac11-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fac11-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fac11-108">Метод GetModule</span><span class="sxs-lookup"><span data-stu-id="fac11-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="fac11-109">Возвращает модуль, в котором определен этот класс.</span><span class="sxs-lookup"><span data-stu-id="fac11-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="fac11-110">Метод GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="fac11-110">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="fac11-111">Получает значение указанного статического поля.</span><span class="sxs-lookup"><span data-stu-id="fac11-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="fac11-112">Метод GetToken</span><span class="sxs-lookup"><span data-stu-id="fac11-112">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|<span data-ttu-id="fac11-113">Возвращает `TypeDef` токен метаданных для этого класса.</span><span class="sxs-lookup"><span data-stu-id="fac11-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fac11-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="fac11-114">Remarks</span></span>  
 <span data-ttu-id="fac11-115">`ICorDebugClass` Интерфейс представляет универсальный тип, у которого отсутствуют экземпляры.</span><span class="sxs-lookup"><span data-stu-id="fac11-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="fac11-116">Интерфейс ICorDebugType представляет экземпляр универсального типа.</span><span class="sxs-lookup"><span data-stu-id="fac11-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="fac11-117">Например `Hashtable<K, V>` будут представлены в `ICorDebugClass`, тогда как `Hashtable<Int32, String>` будут представлены в `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="fac11-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="fac11-118">Неуниверсальные типы представлены как `ICorDebugClass` и `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="fac11-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="fac11-119">Последний интерфейс впервые появился в .NET Framework версии 2.0 для создания экземпляров типов.</span><span class="sxs-lookup"><span data-stu-id="fac11-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fac11-120">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="fac11-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fac11-121">Требования</span><span class="sxs-lookup"><span data-stu-id="fac11-121">Requirements</span></span>  
 <span data-ttu-id="fac11-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fac11-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fac11-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fac11-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fac11-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fac11-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fac11-125">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fac11-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac11-126">См. также</span><span class="sxs-lookup"><span data-stu-id="fac11-126">See Also</span></span>  
 [<span data-ttu-id="fac11-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fac11-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
