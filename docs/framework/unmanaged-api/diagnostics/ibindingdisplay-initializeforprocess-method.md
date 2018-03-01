---
title: "Метод IBindingDisplay::InitializeForProcess"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 56f55788fcaf08507f413a03c5364ce3bcdbbf3c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="5860e-102">Метод IBindingDisplay::InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="5860e-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="5860e-103">Инициализирует [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="5860e-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5860e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5860e-104">Syntax</span></span>  
  
```  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5860e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5860e-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="5860e-106">[in] Идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="5860e-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5860e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="5860e-107">Remarks</span></span>  
 <span data-ttu-id="5860e-108">Отладчик вызывает `InitializeForProcess` метод во время создания для инициализации отображения привязки.</span><span class="sxs-lookup"><span data-stu-id="5860e-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="5860e-109">`InitializeForProcess`должен быть вызван во время создания перед любой другой метод для `IBindingDisplay` вызывается.</span><span class="sxs-lookup"><span data-stu-id="5860e-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5860e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5860e-110">Requirements</span></span>  
 <span data-ttu-id="5860e-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5860e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5860e-112">**Заголовок:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="5860e-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="5860e-113">**Библиотека:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="5860e-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="5860e-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5860e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5860e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5860e-115">See Also</span></span>  
 [<span data-ttu-id="5860e-116">Интерфейс IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="5860e-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
