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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b830af5d59c0eb177d815451ecedbdc14121aaad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964759"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="98570-102">Интерфейс ICorDebugType</span><span class="sxs-lookup"><span data-stu-id="98570-102">ICorDebugType Interface</span></span>
<span data-ttu-id="98570-103">Представляет тип — базовый или сложный (то есть определяемый пользователем).</span><span class="sxs-lookup"><span data-stu-id="98570-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="98570-104">Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.</span><span class="sxs-lookup"><span data-stu-id="98570-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98570-105">Методы</span><span class="sxs-lookup"><span data-stu-id="98570-105">Methods</span></span>  
  
|<span data-ttu-id="98570-106">Метод</span><span class="sxs-lookup"><span data-stu-id="98570-106">Method</span></span>|<span data-ttu-id="98570-107">Описание</span><span class="sxs-lookup"><span data-stu-id="98570-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98570-108">Метод EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="98570-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="98570-109">Возвращает указатель интерфейса на ICorDebugTypeEnum, который ссылается на универсальные <xref:System.Type> параметры класса, на который ссылается this `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="98570-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="98570-110">Метод GetBase</span><span class="sxs-lookup"><span data-stu-id="98570-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="98570-111">Возвращает указатель интерфейса на объект `ICorDebugType` , который ссылается на базовый класс класса, на который ссылается этот `ICorDebugType`класс, если он существует.</span><span class="sxs-lookup"><span data-stu-id="98570-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="98570-112">Метод GetClass</span><span class="sxs-lookup"><span data-stu-id="98570-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="98570-113">Возвращает указатель интерфейса на объект ICorDebugClass, который ссылается на типизированный конструктор этого `ICorDebugType`объекта.</span><span class="sxs-lookup"><span data-stu-id="98570-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="98570-114">Метод GetFirstTypeParameter</span><span class="sxs-lookup"><span data-stu-id="98570-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="98570-115">Возвращает указатель интерфейса на объект `ICorDebugType` , который ссылается на первый универсальный <xref:System.Type> параметр для конструктора класса, на который ссылается this. `ICorDebugType`</span><span class="sxs-lookup"><span data-stu-id="98570-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="98570-116">Метод GetRank</span><span class="sxs-lookup"><span data-stu-id="98570-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="98570-117">Возвращает число измерений в типе массива.</span><span class="sxs-lookup"><span data-stu-id="98570-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="98570-118">Метод GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="98570-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="98570-119">Возвращает указатель интерфейса на объект ICorDebugValue, содержащий значение статического поля, на которое ссылается заданный токен поля в указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="98570-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="98570-120">Метод GetType</span><span class="sxs-lookup"><span data-stu-id="98570-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="98570-121">Возвращает значение корелементтипе, описывающее собственный тип среды <xref:System.Type> CLR, на который ссылается this. `ICorDebugType`</span><span class="sxs-lookup"><span data-stu-id="98570-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98570-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="98570-122">Remarks</span></span>  
 <span data-ttu-id="98570-123">Если тип является универсальным, `ICorDebugClass` представляет тип, не являющийся экземпляром.</span><span class="sxs-lookup"><span data-stu-id="98570-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="98570-124">`ICorDebugType` Интерфейс представляет экземпляр универсального типа.</span><span class="sxs-lookup"><span data-stu-id="98570-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="98570-125">Например, таблица Hashtable\<K, V > будет представлена в `ICorDebugClass`, тогда как Hashtable\< `ICorDebugType`Int32, String > будет представлена.</span><span class="sxs-lookup"><span data-stu-id="98570-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="98570-126">Типы, не являющиеся универсальными, представлены `ICorDebugClass` как `ICorDebugType`, так и.</span><span class="sxs-lookup"><span data-stu-id="98570-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="98570-127">Последний интерфейс появился в .NET Framework версии 2,0 для обработки создания экземпляра типа.</span><span class="sxs-lookup"><span data-stu-id="98570-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98570-128">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="98570-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98570-129">Требования</span><span class="sxs-lookup"><span data-stu-id="98570-129">Requirements</span></span>  
 <span data-ttu-id="98570-130">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98570-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98570-131">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="98570-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98570-132">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="98570-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98570-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98570-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98570-134">См. также</span><span class="sxs-lookup"><span data-stu-id="98570-134">See also</span></span>

- [<span data-ttu-id="98570-135">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="98570-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
