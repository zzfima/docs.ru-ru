---
title: Интерфейс ICorDebugType2
ms.date: 03/30/2017
api_name:
- ICorDebugType2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType2
helpviewer_keywords:
- ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 878941f7af71fa5e3de8e38c4a68a66cb964983d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223164"
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="8e8e1-102">Интерфейс ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="8e8e1-102">ICorDebugType2 Interface</span></span>
<span data-ttu-id="8e8e1-103">Расширяет интерфейс ICorDebugType для извлечения идентификатора типа базового типа или сложного типа (определяемый пользователем).</span><span class="sxs-lookup"><span data-stu-id="8e8e1-103">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e8e1-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8e8e1-104">Methods</span></span>  
  
|<span data-ttu-id="8e8e1-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8e8e1-105">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="8e8e1-106">Метод GetTypeID</span><span class="sxs-lookup"><span data-stu-id="8e8e1-106">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md)|<span data-ttu-id="8e8e1-107">Получает [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) для этого типа.</span><span class="sxs-lookup"><span data-stu-id="8e8e1-107">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e8e1-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="8e8e1-108">Remarks</span></span>  
 <span data-ttu-id="8e8e1-109">Этот интерфейс является логическим расширением интерфейса ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="8e8e1-109">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e8e1-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="8e8e1-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e8e1-111">Пример</span><span class="sxs-lookup"><span data-stu-id="8e8e1-111">Example</span></span>  
 <span data-ttu-id="8e8e1-112">В следующем фрагменте кода показано использование [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="8e8e1-112">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="8e8e1-113">Требования</span><span class="sxs-lookup"><span data-stu-id="8e8e1-113">Requirements</span></span>  
 <span data-ttu-id="8e8e1-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e8e1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e8e1-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e8e1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e8e1-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e8e1-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8e8e1-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8e8e1-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8e8e1-118">См. также</span><span class="sxs-lookup"><span data-stu-id="8e8e1-118">See also</span></span>

- [<span data-ttu-id="8e8e1-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8e8e1-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
