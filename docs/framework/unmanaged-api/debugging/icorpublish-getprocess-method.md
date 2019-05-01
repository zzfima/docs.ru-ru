---
title: Метод ICorPublish::GetProcess
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 021068caa8f1ad2c64e5ca3d18ea25dc827563a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986704"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="5369e-102">Метод ICorPublish::GetProcess</span><span class="sxs-lookup"><span data-stu-id="5369e-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="5369e-103">Получает [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) экземпляр, представляющий процесс с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="5369e-103">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5369e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5369e-104">Syntax</span></span>  
  
```  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5369e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5369e-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="5369e-106">[in] Идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="5369e-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="5369e-107">[out] Указатель на адрес `ICorPublishProcess` экземпляр, представляющий процесс.</span><span class="sxs-lookup"><span data-stu-id="5369e-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5369e-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="5369e-108">Remarks</span></span>  
 <span data-ttu-id="5369e-109">`GetProcess` завершается неудачей, если процесс не существует или не является управляемым процессом, который можно отлаживать текущим пользователем.</span><span class="sxs-lookup"><span data-stu-id="5369e-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5369e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5369e-110">Requirements</span></span>  
 <span data-ttu-id="5369e-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5369e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5369e-112">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="5369e-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5369e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5369e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5369e-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5369e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5369e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5369e-115">See also</span></span>

- [<span data-ttu-id="5369e-116">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="5369e-116">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
