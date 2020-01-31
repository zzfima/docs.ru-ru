---
title: Интерфейс ICorDebugILFrame2
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
ms.openlocfilehash: c5fa0a67309e23c02393b70d849af3884dfd0adf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788544"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="0eddf-102">Интерфейс ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="0eddf-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="0eddf-103">Логическое расширение интерфейса ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="0eddf-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0eddf-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0eddf-104">Methods</span></span>  
  
|<span data-ttu-id="0eddf-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0eddf-105">Method</span></span>|<span data-ttu-id="0eddf-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0eddf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0eddf-107">Метод EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="0eddf-107">EnumerateTypeParameters Method</span></span>](icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="0eddf-108">Возвращает объект ICorDebugTypeEnum, содержащий параметры <xref:System.Type> в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="0eddf-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="0eddf-109">Метод RemapFunction</span><span class="sxs-lookup"><span data-stu-id="0eddf-109">RemapFunction Method</span></span>](icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="0eddf-110">Повторно сопоставляет отредактированную функцию, указывая новое смещение MSIL.</span><span class="sxs-lookup"><span data-stu-id="0eddf-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0eddf-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="0eddf-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0eddf-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="0eddf-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eddf-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0eddf-113">Requirements</span></span>  
 <span data-ttu-id="0eddf-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0eddf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eddf-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0eddf-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0eddf-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0eddf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0eddf-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eddf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eddf-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="0eddf-118">See also</span></span>

- [<span data-ttu-id="0eddf-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0eddf-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
