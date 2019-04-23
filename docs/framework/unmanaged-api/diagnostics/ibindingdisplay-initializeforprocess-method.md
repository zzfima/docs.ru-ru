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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197884"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="04272-102">Метод IBindingDisplay::InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="04272-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="04272-103">Инициализирует [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="04272-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04272-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04272-104">Syntax</span></span>  
  
```  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04272-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="04272-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="04272-106">[in] Идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="04272-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04272-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="04272-107">Remarks</span></span>  
 <span data-ttu-id="04272-108">Отладчик вызывает `InitializeForProcess` метод во время создания для инициализации отображения привязки.</span><span class="sxs-lookup"><span data-stu-id="04272-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="04272-109">`InitializeForProcess` должен вызываться во время создания перед вызовом любого другого метода на `IBindingDisplay` вызывается.</span><span class="sxs-lookup"><span data-stu-id="04272-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04272-110">Требования</span><span class="sxs-lookup"><span data-stu-id="04272-110">Requirements</span></span>  
 <span data-ttu-id="04272-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04272-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04272-112">**Заголовок.** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="04272-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="04272-113">**Библиотека:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="04272-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="04272-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04272-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04272-115">См. также</span><span class="sxs-lookup"><span data-stu-id="04272-115">See also</span></span>

- [<span data-ttu-id="04272-116">Интерфейс IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="04272-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
