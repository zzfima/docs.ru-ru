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
ms.openlocfilehash: 46f047dbec7ff008873540806b76ffe7085086b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178424"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="aa017-102">Метод ICorPublish::GetProcess</span><span class="sxs-lookup"><span data-stu-id="aa017-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="aa017-103">Получает экземпляр [ICorPublishProcess,](icorpublishprocess-interface.md) представляющий процесс с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="aa017-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa017-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa017-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa017-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aa017-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="aa017-106">(в) Идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="aa017-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="aa017-107">(ваут) Указатель на адрес `ICorPublishProcess` экземпляра, представляющего процесс.</span><span class="sxs-lookup"><span data-stu-id="aa017-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa017-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="aa017-108">Remarks</span></span>  
 <span data-ttu-id="aa017-109">`GetProcess`сбой, если процесс не существует, или не является управляемым процессом, который может быть отдигирован текущим пользователем.</span><span class="sxs-lookup"><span data-stu-id="aa017-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa017-110">Требования</span><span class="sxs-lookup"><span data-stu-id="aa017-110">Requirements</span></span>  
 <span data-ttu-id="aa017-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa017-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa017-112">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="aa017-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="aa017-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa017-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa017-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa017-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa017-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aa017-115">See also</span></span>

- [<span data-ttu-id="aa017-116">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="aa017-116">ICorPublish Interface</span></span>](icorpublish-interface.md)
