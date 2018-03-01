---
title: "Метод IBindingDisplay::GetCurrentDisplay"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cce7638bfe6ffe0d4b5f7f9a64aaff0c59c860cb
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="fa047-102">Метод IBindingDisplay::GetCurrentDisplay</span><span class="sxs-lookup"><span data-stu-id="fa047-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="fa047-103">Возвращает сведения об отображении текущей привязки.</span><span class="sxs-lookup"><span data-stu-id="fa047-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa047-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa047-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa047-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fa047-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="fa047-106">[out, retval] Указатель на массив safearray, содержащий сведения об отображении привязки.</span><span class="sxs-lookup"><span data-stu-id="fa047-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa047-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="fa047-107">Remarks</span></span>  
 <span data-ttu-id="fa047-108">[IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) метод должен ранее успешно завершена, и программа должна быть остановлена с помощью отладчика.</span><span class="sxs-lookup"><span data-stu-id="fa047-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="fa047-109">Вызывающий объект должен освободить возвращаемый `SAFEARRAY` памяти с помощью [SafeArrayDestroy](http://msdn.microsoft.com/library/fc94f7e7-b903-4c78-905c-54df1f8d13fa).</span><span class="sxs-lookup"><span data-stu-id="fa047-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](http://msdn.microsoft.com/library/fc94f7e7-b903-4c78-905c-54df1f8d13fa).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa047-110">Требования</span><span class="sxs-lookup"><span data-stu-id="fa047-110">Requirements</span></span>  
 <span data-ttu-id="fa047-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa047-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa047-112">**Заголовок:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="fa047-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="fa047-113">**Библиотека:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="fa047-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="fa047-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa047-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa047-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fa047-115">See Also</span></span>  
 [<span data-ttu-id="fa047-116">Интерфейс IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="fa047-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 [<span data-ttu-id="fa047-117">Метод InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="fa047-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
