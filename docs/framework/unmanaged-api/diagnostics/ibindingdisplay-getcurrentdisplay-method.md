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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d075aeeb904469613999829a1444511d069b9918
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775978"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="8dc1b-102">Метод IBindingDisplay::GetCurrentDisplay</span><span class="sxs-lookup"><span data-stu-id="8dc1b-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="8dc1b-103">Возвращает данные для отображения текущей привязки.</span><span class="sxs-lookup"><span data-stu-id="8dc1b-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dc1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8dc1b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dc1b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8dc1b-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="8dc1b-106">[out, retval] Указатель на массив safearray, содержащий сведения об отображении привязки.</span><span class="sxs-lookup"><span data-stu-id="8dc1b-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8dc1b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8dc1b-107">Remarks</span></span>  
 <span data-ttu-id="8dc1b-108">[IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) метод должен ранее успешно и программа должна быть остановлена с помощью отладчика.</span><span class="sxs-lookup"><span data-stu-id="8dc1b-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="8dc1b-109">Вызывающий объект должен освободить возвращенного `SAFEARRAY` памяти с помощью [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span><span class="sxs-lookup"><span data-stu-id="8dc1b-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dc1b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8dc1b-110">Requirements</span></span>  
 <span data-ttu-id="8dc1b-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8dc1b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dc1b-112">**Заголовок.** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="8dc1b-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="8dc1b-113">**Библиотека:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="8dc1b-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="8dc1b-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dc1b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dc1b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="8dc1b-115">See also</span></span>

- [<span data-ttu-id="8dc1b-116">Интерфейс IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="8dc1b-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
- [<span data-ttu-id="8dc1b-117">Метод InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="8dc1b-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
