---
title: ICorDebugILFrame2 интерфейс1
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccb39609b37aff09ac7890df562d6c08e3c3c159
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412439"
---
# <a name="icordebugilframe2-interface1"></a><span data-ttu-id="868a7-102">ICorDebugILFrame2 интерфейс1</span><span class="sxs-lookup"><span data-stu-id="868a7-102">ICorDebugILFrame2 Interface1</span></span>
<span data-ttu-id="868a7-103">Логическое расширение интерфейса ICorDebugILFrame-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="868a7-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="868a7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="868a7-104">Methods</span></span>  
  
|<span data-ttu-id="868a7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="868a7-105">Method</span></span>|<span data-ttu-id="868a7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="868a7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="868a7-107">Метод EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="868a7-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="868a7-108">Возвращает объект ICorDebugTypeEnum, содержащий <xref:System.Type> параметры в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="868a7-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="868a7-109">Метод RemapFunction</span><span class="sxs-lookup"><span data-stu-id="868a7-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="868a7-110">Перераспределяет отредактированную функцию путем указания нового смещения MSIL.</span><span class="sxs-lookup"><span data-stu-id="868a7-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="868a7-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="868a7-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="868a7-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="868a7-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="868a7-113">Требования</span><span class="sxs-lookup"><span data-stu-id="868a7-113">Requirements</span></span>  
 <span data-ttu-id="868a7-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="868a7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="868a7-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="868a7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="868a7-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="868a7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="868a7-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="868a7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="868a7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="868a7-118">See Also</span></span>  
 [<span data-ttu-id="868a7-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="868a7-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
