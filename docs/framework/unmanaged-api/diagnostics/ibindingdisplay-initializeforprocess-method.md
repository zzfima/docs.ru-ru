---
title: Метод IBindingDisplay::InitializeForProcess
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aa1e85751f90c34d40e88207af5c7eed2dd1bb82
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197884"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="26df8-102">Метод IBindingDisplay::InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="26df8-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="26df8-103">Инициализирует [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="26df8-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26df8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26df8-104">Syntax</span></span>  
  
```  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26df8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="26df8-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="26df8-106">[in] Идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="26df8-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26df8-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="26df8-107">Remarks</span></span>  
 <span data-ttu-id="26df8-108">Отладчик вызывает `InitializeForProcess` метод во время создания для инициализации отображения привязки.</span><span class="sxs-lookup"><span data-stu-id="26df8-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> `InitializeForProcess` <span data-ttu-id="26df8-109">должен вызываться во время создания перед вызовом любого другого метода на `IBindingDisplay` вызывается.</span><span class="sxs-lookup"><span data-stu-id="26df8-109">must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26df8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="26df8-110">Requirements</span></span>  
 <span data-ttu-id="26df8-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26df8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26df8-112">**Заголовок.** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="26df8-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="26df8-113">**Библиотека:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="26df8-113">**Library:** BindingDisplay.idl</span></span>  
  
 **<span data-ttu-id="26df8-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="26df8-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="26df8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="26df8-115">See also</span></span>

- [<span data-ttu-id="26df8-116">Интерфейс IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="26df8-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
