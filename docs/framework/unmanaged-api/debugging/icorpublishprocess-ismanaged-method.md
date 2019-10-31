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
ms.openlocfilehash: ad3a357a98cb5ed28a34e4076b5e145903ceaf91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103503"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="32518-102">Метод ICorPublishProcess::IsManaged</span><span class="sxs-lookup"><span data-stu-id="32518-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="32518-103">Возвращает значение, указывающее, известно ли для процесса, на который ссылается этот [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) , управляемый код.</span><span class="sxs-lookup"><span data-stu-id="32518-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32518-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32518-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32518-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="32518-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="32518-106">заполняет Указатель на логическое значение, указывающее, имеет ли процесс управляемый код.</span><span class="sxs-lookup"><span data-stu-id="32518-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="32518-107">Значение `true`, если процесс имеет управляемый код; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="32518-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32518-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="32518-108">Remarks</span></span>  
 <span data-ttu-id="32518-109">Поскольку текущая версия `ICorPublishProcess` разрешает доступ только к процессам с управляемым кодом, `IsManaged` всегда возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="32518-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32518-110">Требования</span><span class="sxs-lookup"><span data-stu-id="32518-110">Requirements</span></span>  
 <span data-ttu-id="32518-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32518-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32518-112">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="32518-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="32518-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32518-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32518-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32518-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32518-115">См. также</span><span class="sxs-lookup"><span data-stu-id="32518-115">See also</span></span>

- [<span data-ttu-id="32518-116">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="32518-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
