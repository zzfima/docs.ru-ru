---
title: ICorDebugType интерфейс1
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
ms.openlocfilehash: de2871b406bb9da84d20d7c526ad4a703baae409
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugtype-interface1"></a><span data-ttu-id="b880d-102">ICorDebugType интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b880d-102">ICorDebugType Interface1</span></span>
<span data-ttu-id="b880d-103">Представляет тип, либо простой или сложной (который определяемый пользователем).</span><span class="sxs-lookup"><span data-stu-id="b880d-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="b880d-104">Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.</span><span class="sxs-lookup"><span data-stu-id="b880d-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b880d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b880d-105">Methods</span></span>  
  
|<span data-ttu-id="b880d-106">Метод</span><span class="sxs-lookup"><span data-stu-id="b880d-106">Method</span></span>|<span data-ttu-id="b880d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b880d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b880d-108">Метод EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="b880d-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="b880d-109">Получает указатель интерфейса на ICorDebugTypeEnum, который ссылается на параметр универсального <xref:System.Type> параметры типа класса, который ссылается этот `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="b880d-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="b880d-110">Метод GetBase</span><span class="sxs-lookup"><span data-stu-id="b880d-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="b880d-111">Возвращает указатель интерфейса `ICorDebugType` , ссылается на базовый класс для класса, который ссылается этот `ICorDebugType`, если он существует.</span><span class="sxs-lookup"><span data-stu-id="b880d-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="b880d-112">Метод GetClass</span><span class="sxs-lookup"><span data-stu-id="b880d-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="b880d-113">Получает указатель интерфейса на ICorDebugClass, который ссылается на типизированный конструктор `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="b880d-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="b880d-114">Метод GetFirstTypeParameter</span><span class="sxs-lookup"><span data-stu-id="b880d-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="b880d-115">Возвращает указатель интерфейса `ICorDebugType` , ссылается на первый универсальный <xref:System.Type> параметра для конструктора класса, упоминаемой в этом `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="b880d-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="b880d-116">Метод GetRank</span><span class="sxs-lookup"><span data-stu-id="b880d-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="b880d-117">Возвращает число измерений в тип массива.</span><span class="sxs-lookup"><span data-stu-id="b880d-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="b880d-118">Метод GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="b880d-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="b880d-119">Возвращает указатель на интерфейс ICorDebugValue, содержащий значение статического поля, который ссылается указанное поле токена в указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="b880d-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="b880d-120">Метод GetType</span><span class="sxs-lookup"><span data-stu-id="b880d-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="b880d-121">Возвращает значение CorElementType, которое описывает собственный тип общеязыковая среда выполнения <xref:System.Type> ссылается этот `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="b880d-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b880d-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="b880d-122">Remarks</span></span>  
 <span data-ttu-id="b880d-123">Если тип является универсальным, `ICorDebugClass` представляет типа без экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b880d-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="b880d-124">`ICorDebugType` Интерфейс представляет экземпляр универсального типа.</span><span class="sxs-lookup"><span data-stu-id="b880d-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="b880d-125">Например, хэш-таблицы\<K, V > может быть представлена `ICorDebugClass`, тогда как хэш-таблицы\<Int32, String > будут представлены в `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="b880d-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="b880d-126">Неуниверсальные типы представлены как `ICorDebugClass` и `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="b880d-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="b880d-127">Последний интерфейс впервые появился в .NET Framework версии 2.0 для создания экземпляров типов.</span><span class="sxs-lookup"><span data-stu-id="b880d-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b880d-128">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="b880d-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b880d-129">Требования</span><span class="sxs-lookup"><span data-stu-id="b880d-129">Requirements</span></span>  
 <span data-ttu-id="b880d-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b880d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b880d-131">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b880d-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b880d-132">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b880d-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b880d-133">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b880d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b880d-134">См. также</span><span class="sxs-lookup"><span data-stu-id="b880d-134">See Also</span></span>  
 [<span data-ttu-id="b880d-135">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b880d-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
