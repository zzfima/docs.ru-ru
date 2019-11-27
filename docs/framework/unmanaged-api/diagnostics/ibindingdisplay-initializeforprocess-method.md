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
ms.openlocfilehash: bb796a12868cc3e44394ab493f7838dc48ab4dc5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448494"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="f971a-102">Метод IBindingDisplay::InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="f971a-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="f971a-103">Инициализирует объект [ибиндингдисплай](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f971a-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f971a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f971a-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f971a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f971a-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="f971a-106">окне Идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="f971a-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f971a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f971a-107">Remarks</span></span>  
 <span data-ttu-id="f971a-108">Отладчик вызывает метод `InitializeForProcess` во время создания, чтобы инициализировать отображение привязки.</span><span class="sxs-lookup"><span data-stu-id="f971a-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="f971a-109">`InitializeForProcess` должны вызываться во время создания до вызова любого другого метода в `IBindingDisplay`.</span><span class="sxs-lookup"><span data-stu-id="f971a-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f971a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f971a-110">Requirements</span></span>  
 <span data-ttu-id="f971a-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f971a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f971a-112">**Заголовок:** Биндингдисплай. h</span><span class="sxs-lookup"><span data-stu-id="f971a-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="f971a-113">**Библиотека:** Биндингдисплай. idl</span><span class="sxs-lookup"><span data-stu-id="f971a-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="f971a-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f971a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f971a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f971a-115">See also</span></span>

- [<span data-ttu-id="f971a-116">Интерфейс IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="f971a-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
