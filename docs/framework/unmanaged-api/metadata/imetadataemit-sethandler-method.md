---
title: "Метод IMetaDataEmit::SetHandler"
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
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ccb35c12e1d9c2fade9d8760d0a2e39807c92de9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="dd4a5-102">Метод IMetaDataEmit::SetHandler</span><span class="sxs-lookup"><span data-stu-id="dd4a5-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="dd4a5-103">Задает метод, который ссылается заданный дескриптор `IUnknown` указатель в виде обратного вызова уведомления для повторного сопоставления маркера.</span><span class="sxs-lookup"><span data-stu-id="dd4a5-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd4a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd4a5-104">Syntax</span></span>  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dd4a5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dd4a5-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="dd4a5-106">[in] Обработчик для регистрации.</span><span class="sxs-lookup"><span data-stu-id="dd4a5-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd4a5-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="dd4a5-107">Remarks</span></span>  
 <span data-ttu-id="dd4a5-108">Ядро метаданных отправляет уведомление с помощью метода, предоставляемая `SetHandler`, для компиляторов, не создает записи оптимальным образом и который вы хотите оптимизировать сохраненных записей.</span><span class="sxs-lookup"><span data-stu-id="dd4a5-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="dd4a5-109">Если метод обратного вызова не предоставляется через `SetHandler`, будет выполняться без оптимизации на сохранить за исключением того, где несколько импорта области были объединены с помощью `IMapToken` на слияния для каждой области.</span><span class="sxs-lookup"><span data-stu-id="dd4a5-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd4a5-110">Требования</span><span class="sxs-lookup"><span data-stu-id="dd4a5-110">Requirements</span></span>  
 <span data-ttu-id="dd4a5-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd4a5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd4a5-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dd4a5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dd4a5-113">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd4a5-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd4a5-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd4a5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd4a5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="dd4a5-115">See Also</span></span>  
 [<span data-ttu-id="dd4a5-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="dd4a5-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="dd4a5-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="dd4a5-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
