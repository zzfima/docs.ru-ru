---
title: Метод IBindingDisplay::GetCurrentDisplay
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
ms.openlocfilehash: 9294dbf1caddd4b607185de54efd2b4764e6ca35
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448506"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="cdb87-102">Метод IBindingDisplay::GetCurrentDisplay</span><span class="sxs-lookup"><span data-stu-id="cdb87-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="cdb87-103">Returns the current binding display information.</span><span class="sxs-lookup"><span data-stu-id="cdb87-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdb87-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cdb87-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdb87-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cdb87-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="cdb87-106">[out, retval] A pointer to a safearray containing the binding display information.</span><span class="sxs-lookup"><span data-stu-id="cdb87-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdb87-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="cdb87-107">Remarks</span></span>  
 <span data-ttu-id="cdb87-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span><span class="sxs-lookup"><span data-stu-id="cdb87-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="cdb87-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span><span class="sxs-lookup"><span data-stu-id="cdb87-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdb87-110">Требования</span><span class="sxs-lookup"><span data-stu-id="cdb87-110">Requirements</span></span>  
 <span data-ttu-id="cdb87-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdb87-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdb87-112">**Header:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="cdb87-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="cdb87-113">**Library:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="cdb87-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="cdb87-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdb87-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdb87-115">См. также</span><span class="sxs-lookup"><span data-stu-id="cdb87-115">See also</span></span>

- [<span data-ttu-id="cdb87-116">Интерфейс IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="cdb87-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
- [<span data-ttu-id="cdb87-117">Метод InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="cdb87-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
