---
title: Интерфейс ICorDebugAppDomain2
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c6ef901f43cd6568f17657ed8e58bc2cc2cc0a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922269"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="bcc71-102">Интерфейс ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="bcc71-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="bcc71-103">Предоставляет методы для работы с массивами, указателями, указатели на функции и ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="bcc71-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="bcc71-104">Этот интерфейс является расширением интерфейса ICorDebugAppDomain.</span><span class="sxs-lookup"><span data-stu-id="bcc71-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bcc71-105">Методы</span><span class="sxs-lookup"><span data-stu-id="bcc71-105">Methods</span></span>  
  
|<span data-ttu-id="bcc71-106">Метод</span><span class="sxs-lookup"><span data-stu-id="bcc71-106">Method</span></span>|<span data-ttu-id="bcc71-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bcc71-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bcc71-108">Метод GetArrayOrPointerType</span><span class="sxs-lookup"><span data-stu-id="bcc71-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="bcc71-109">Получает массив указанного типа, указатель или ссылка на указанный тип.</span><span class="sxs-lookup"><span data-stu-id="bcc71-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="bcc71-110">Метод GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="bcc71-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="bcc71-111">Получает указатель на функцию с заданной подписью.</span><span class="sxs-lookup"><span data-stu-id="bcc71-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcc71-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="bcc71-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bcc71-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="bcc71-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcc71-114">Требования</span><span class="sxs-lookup"><span data-stu-id="bcc71-114">Requirements</span></span>  
 <span data-ttu-id="bcc71-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcc71-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcc71-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bcc71-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bcc71-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcc71-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcc71-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcc71-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcc71-119">См. также</span><span class="sxs-lookup"><span data-stu-id="bcc71-119">See also</span></span>

- [<span data-ttu-id="bcc71-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bcc71-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
