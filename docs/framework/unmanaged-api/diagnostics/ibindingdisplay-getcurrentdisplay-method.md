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
ms.openlocfilehash: 472e06c3a00762a7bb012fbcb525d8e0b3a9271a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162262"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="2e47a-102">Метод IBindingDisplay::GetCurrentDisplay</span><span class="sxs-lookup"><span data-stu-id="2e47a-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="2e47a-103">Возвращает данные для отображения текущей привязки.</span><span class="sxs-lookup"><span data-stu-id="2e47a-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e47a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e47a-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e47a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e47a-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="2e47a-106">[out, retval] Указатель на массив safearray, содержащий сведения об отображении привязки.</span><span class="sxs-lookup"><span data-stu-id="2e47a-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e47a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="2e47a-107">Remarks</span></span>  
 <span data-ttu-id="2e47a-108">[IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) метод должен ранее успешно и программа должна быть остановлена с помощью отладчика.</span><span class="sxs-lookup"><span data-stu-id="2e47a-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="2e47a-109">Вызывающий объект должен освободить возвращенного `SAFEARRAY` памяти с помощью [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span><span class="sxs-lookup"><span data-stu-id="2e47a-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e47a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2e47a-110">Requirements</span></span>  
 <span data-ttu-id="2e47a-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e47a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e47a-112">**Заголовок.** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="2e47a-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="2e47a-113">**Библиотека:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="2e47a-113">**Library:** BindingDisplay.idl</span></span>  
  
 **<span data-ttu-id="2e47a-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2e47a-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2e47a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2e47a-115">See also</span></span>

- [<span data-ttu-id="2e47a-116">Интерфейс IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="2e47a-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
- [<span data-ttu-id="2e47a-117">Метод InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="2e47a-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
