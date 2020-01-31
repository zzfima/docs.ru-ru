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
ms.openlocfilehash: 6f9bcec66ff613d19c1198ac9849ca28c978f537
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788944"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="b7d22-102">Интерфейс ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="b7d22-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="b7d22-103">Предоставляет методы для работы с массивами, указателями, указателями функций и ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="b7d22-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="b7d22-104">Этот интерфейс является расширением интерфейса ICorDebugAppDomain.</span><span class="sxs-lookup"><span data-stu-id="b7d22-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7d22-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b7d22-105">Methods</span></span>  
  
|<span data-ttu-id="b7d22-106">Метод</span><span class="sxs-lookup"><span data-stu-id="b7d22-106">Method</span></span>|<span data-ttu-id="b7d22-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b7d22-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7d22-108">Метод GetArrayOrPointerType</span><span class="sxs-lookup"><span data-stu-id="b7d22-108">GetArrayOrPointerType Method</span></span>](icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="b7d22-109">Возвращает массив указанного типа или указатель или ссылку на указанный тип.</span><span class="sxs-lookup"><span data-stu-id="b7d22-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="b7d22-110">Метод GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="b7d22-110">GetFunctionPointerType</span></span>](icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="b7d22-111">Возвращает указатель на функцию с заданной сигнатурой.</span><span class="sxs-lookup"><span data-stu-id="b7d22-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7d22-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="b7d22-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b7d22-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="b7d22-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7d22-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b7d22-114">Requirements</span></span>  
 <span data-ttu-id="b7d22-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7d22-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7d22-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7d22-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7d22-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7d22-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7d22-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7d22-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d22-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="b7d22-119">See also</span></span>

- [<span data-ttu-id="b7d22-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b7d22-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
