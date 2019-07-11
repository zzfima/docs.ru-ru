---
title: Метод ICorPublishProcess::GetProcessID
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29427bab938437c40d0edb5676a2f8f76cbb6691
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764860"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="78ad9-102">Метод ICorPublishProcess::GetProcessID</span><span class="sxs-lookup"><span data-stu-id="78ad9-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="78ad9-103">Получает идентификатор операционной системы для этого процесса.</span><span class="sxs-lookup"><span data-stu-id="78ad9-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78ad9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78ad9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78ad9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="78ad9-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="78ad9-106">[out] Указатель на идентификатор процесса, представленный этим [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="78ad9-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78ad9-107">Требования</span><span class="sxs-lookup"><span data-stu-id="78ad9-107">Requirements</span></span>  
 <span data-ttu-id="78ad9-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78ad9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78ad9-109">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="78ad9-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="78ad9-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78ad9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78ad9-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78ad9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78ad9-112">См. также</span><span class="sxs-lookup"><span data-stu-id="78ad9-112">See also</span></span>

- [<span data-ttu-id="78ad9-113">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="78ad9-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
