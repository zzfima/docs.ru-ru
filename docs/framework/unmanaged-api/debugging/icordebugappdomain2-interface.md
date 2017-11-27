---
title: "Интерфейс1 ICorDebugAppDomain2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain2
helpviewer_keywords: ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ebd1e504cbf2f74ad82e7fea6b6c3f355a1bda34
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain2-interface1"></a><span data-ttu-id="dbd20-102">Интерфейс1 ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="dbd20-102">ICorDebugAppDomain2 Interface1</span></span>
<span data-ttu-id="dbd20-103">Предоставляет методы для работы с массивами, указателями, указатели на функции и ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="dbd20-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="dbd20-104">Этот интерфейс является расширением интерфейса ICorDebugAppDomain.</span><span class="sxs-lookup"><span data-stu-id="dbd20-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dbd20-105">Методы</span><span class="sxs-lookup"><span data-stu-id="dbd20-105">Methods</span></span>  
  
|<span data-ttu-id="dbd20-106">Метод</span><span class="sxs-lookup"><span data-stu-id="dbd20-106">Method</span></span>|<span data-ttu-id="dbd20-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dbd20-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dbd20-108">Метод GetArrayOrPointerType</span><span class="sxs-lookup"><span data-stu-id="dbd20-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="dbd20-109">Возвращает массив указанного типа, указатель или ссылку на указанный тип.</span><span class="sxs-lookup"><span data-stu-id="dbd20-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="dbd20-110">Метод GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="dbd20-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="dbd20-111">Возвращает указатель на функцию с заданной подписью.</span><span class="sxs-lookup"><span data-stu-id="dbd20-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbd20-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="dbd20-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dbd20-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="dbd20-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbd20-114">Требования</span><span class="sxs-lookup"><span data-stu-id="dbd20-114">Requirements</span></span>  
 <span data-ttu-id="dbd20-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbd20-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbd20-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbd20-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbd20-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbd20-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbd20-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbd20-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd20-119">См. также</span><span class="sxs-lookup"><span data-stu-id="dbd20-119">See Also</span></span>  
 [<span data-ttu-id="dbd20-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="dbd20-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
