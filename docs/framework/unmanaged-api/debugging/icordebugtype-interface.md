---
title: Интерфейс ICorDebugType
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
ms.openlocfilehash: 4f3f553ed5dc93433610365e0dae5bee54863de5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129627"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="99244-102">Интерфейс ICorDebugType</span><span class="sxs-lookup"><span data-stu-id="99244-102">ICorDebugType Interface</span></span>
<span data-ttu-id="99244-103">Представляет тип — базовый или сложный (то есть определяемый пользователем).</span><span class="sxs-lookup"><span data-stu-id="99244-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="99244-104">Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.</span><span class="sxs-lookup"><span data-stu-id="99244-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="99244-105">Методы</span><span class="sxs-lookup"><span data-stu-id="99244-105">Methods</span></span>  
  
|<span data-ttu-id="99244-106">Метод</span><span class="sxs-lookup"><span data-stu-id="99244-106">Method</span></span>|<span data-ttu-id="99244-107">Описание</span><span class="sxs-lookup"><span data-stu-id="99244-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="99244-108">Метод EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="99244-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="99244-109">Возвращает указатель интерфейса на ICorDebugTypeEnum, который ссылается на универсальные параметры <xref:System.Type> класса, на который ссылается этот `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="99244-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="99244-110">Метод GetBase</span><span class="sxs-lookup"><span data-stu-id="99244-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="99244-111">Возвращает указатель интерфейса на `ICorDebugType`, ссылающийся на базовый класс класса, на который ссылается этот `ICorDebugType`, если он существует.</span><span class="sxs-lookup"><span data-stu-id="99244-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="99244-112">Метод GetClass</span><span class="sxs-lookup"><span data-stu-id="99244-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="99244-113">Возвращает указатель интерфейса на объект ICorDebugClass, который ссылается на типизированный конструктор этого `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="99244-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="99244-114">Метод GetFirstTypeParameter</span><span class="sxs-lookup"><span data-stu-id="99244-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="99244-115">Возвращает указатель интерфейса на `ICorDebugType`, который ссылается на первый универсальный параметр <xref:System.Type> для конструктора класса, на который ссылается этот `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="99244-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="99244-116">Метод GetRank</span><span class="sxs-lookup"><span data-stu-id="99244-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="99244-117">Возвращает число измерений в типе массива.</span><span class="sxs-lookup"><span data-stu-id="99244-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="99244-118">Метод GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="99244-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="99244-119">Возвращает указатель интерфейса на объект ICorDebugValue, содержащий значение статического поля, на которое ссылается заданный токен поля в указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="99244-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="99244-120">Метод GetType</span><span class="sxs-lookup"><span data-stu-id="99244-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="99244-121">Возвращает значение Корелементтипе, описывающее собственный тип среды CLR <xref:System.Type> на которую ссылается этот `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="99244-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99244-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="99244-122">Remarks</span></span>  
 <span data-ttu-id="99244-123">Если тип является универсальным, `ICorDebugClass` представляет тип, не являющийся экземпляром.</span><span class="sxs-lookup"><span data-stu-id="99244-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="99244-124">Интерфейс `ICorDebugType` представляет экземпляр универсального типа.</span><span class="sxs-lookup"><span data-stu-id="99244-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="99244-125">Например, хэш-таблица\<K, V > будет представлена `ICorDebugClass`, тогда как Hashtable\<Int32, строка > будет представлена `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="99244-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="99244-126">Типы, не являющиеся универсальными, представляются как `ICorDebugClass`, так и `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="99244-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="99244-127">Последний интерфейс появился в .NET Framework версии 2,0 для обработки создания экземпляра типа.</span><span class="sxs-lookup"><span data-stu-id="99244-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99244-128">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="99244-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99244-129">Требования</span><span class="sxs-lookup"><span data-stu-id="99244-129">Requirements</span></span>  
 <span data-ttu-id="99244-130">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99244-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99244-131">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99244-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99244-132">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99244-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99244-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99244-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99244-134">См. также</span><span class="sxs-lookup"><span data-stu-id="99244-134">See also</span></span>

- [<span data-ttu-id="99244-135">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="99244-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
