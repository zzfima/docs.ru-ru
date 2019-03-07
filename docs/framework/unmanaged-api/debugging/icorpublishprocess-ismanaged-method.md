---
title: Метод ICorPublishProcess::IsManaged
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 404403576b7fd32362a690d470a5ea4b48489d26
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484801"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="2c506-102">Метод ICorPublishProcess::IsManaged</span><span class="sxs-lookup"><span data-stu-id="2c506-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="2c506-103">Получает значение, указывающее, является ли процесс ссылается этот [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) известно, что есть управляемый код.</span><span class="sxs-lookup"><span data-stu-id="2c506-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c506-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c506-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c506-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c506-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="2c506-106">[out] Указатель на логическое значение, указывающее, ли процесс управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="2c506-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="2c506-107">Значение равно `true` Если процесс с управляемым кодом; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="2c506-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c506-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="2c506-108">Remarks</span></span>  
 <span data-ttu-id="2c506-109">Так как текущая версия `ICorPublishProcess` разрешает доступ только к процессам, которые управляемого кода, `IsManaged` всегда возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="2c506-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c506-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2c506-110">Requirements</span></span>  
 <span data-ttu-id="2c506-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c506-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c506-112">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="2c506-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2c506-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c506-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c506-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c506-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c506-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2c506-115">See also</span></span>
- [<span data-ttu-id="2c506-116">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="2c506-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
