---
title: Метод IValidator::FormatEventInfo
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
ms.openlocfilehash: 9b3a6bab8672f3ef3fca5f89c60b03a43477cce5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123299"
---
# <a name="ivalidatorformateventinfo-method"></a><span data-ttu-id="76d5b-102">Метод IValidator::FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="76d5b-102">IValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="76d5b-103">Возвращает сообщение об ошибке, соответствующее указанной ошибке проверки.</span><span class="sxs-lookup"><span data-stu-id="76d5b-103">Gets the error message corresponding to the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76d5b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76d5b-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76d5b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="76d5b-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="76d5b-106">окне Значение HRESULT, которое было передано обработчику ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="76d5b-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="76d5b-107">окне Экземпляр `VEContext`, содержащий контекстные сведения об ошибке проверки.</span><span class="sxs-lookup"><span data-stu-id="76d5b-107">[in] A `VEContext` instance that contains context information about the validation error.</span></span>  
  
 `msg`  
 <span data-ttu-id="76d5b-108">[вход, выход] Строка, содержащая возвращенное сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="76d5b-108">[in, out] A string that contains the returned error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="76d5b-109">окне Максимальная длина сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="76d5b-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="76d5b-110">окне Защищенный массив, содержащий дополнительные параметры, описывающие ошибку.</span><span class="sxs-lookup"><span data-stu-id="76d5b-110">[in] A safe array that contains additional parameters describing the error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76d5b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="76d5b-111">Requirements</span></span>  
 <span data-ttu-id="76d5b-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76d5b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76d5b-113">**Заголовок:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="76d5b-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="76d5b-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="76d5b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76d5b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76d5b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
