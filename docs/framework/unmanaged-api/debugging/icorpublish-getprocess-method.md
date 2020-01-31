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
ms.openlocfilehash: 0368349e6c6a566cb569738bf3bda40eb9f5de96
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790738"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="e5e24-102">Метод ICorPublish::GetProcess</span><span class="sxs-lookup"><span data-stu-id="e5e24-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="e5e24-103">Возвращает экземпляр [ICorPublishProcess](icorpublishprocess-interface.md) , представляющий процесс с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="e5e24-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5e24-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5e24-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5e24-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e5e24-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="e5e24-106">окне Идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="e5e24-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="e5e24-107">заполняет Указатель на адрес экземпляра `ICorPublishProcess`, который представляет процесс.</span><span class="sxs-lookup"><span data-stu-id="e5e24-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5e24-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="e5e24-108">Remarks</span></span>  
 <span data-ttu-id="e5e24-109">`GetProcess` завершается ошибкой, если процесс не существует или не является управляемым процессом, который может быть отлажен текущим пользователем.</span><span class="sxs-lookup"><span data-stu-id="e5e24-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5e24-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e5e24-110">Requirements</span></span>  
 <span data-ttu-id="e5e24-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5e24-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5e24-112">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="e5e24-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e5e24-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5e24-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5e24-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5e24-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5e24-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="e5e24-115">See also</span></span>

- [<span data-ttu-id="e5e24-116">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="e5e24-116">ICorPublish Interface</span></span>](icorpublish-interface.md)
