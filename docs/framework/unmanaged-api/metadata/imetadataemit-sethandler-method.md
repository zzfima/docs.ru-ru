---
title: Метод IMetaDataEmit::SetHandler
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ada84df2a08b992aa178c2fb63c713b05a8937a2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503220"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="a8ab5-102">Метод IMetaDataEmit::SetHandler</span><span class="sxs-lookup"><span data-stu-id="a8ab5-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="a8ab5-103">Задает метод, который ссылается заданный `IUnknown` указатель в виде обратного вызова уведомления для повторного сопоставления маркера.</span><span class="sxs-lookup"><span data-stu-id="a8ab5-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8ab5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8ab5-104">Syntax</span></span>  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8ab5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a8ab5-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="a8ab5-106">[in] Регистрируемый дескриптор.</span><span class="sxs-lookup"><span data-stu-id="a8ab5-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8ab5-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a8ab5-107">Remarks</span></span>  
 <span data-ttu-id="a8ab5-108">Подсистема метаданных отправляет уведомление, используя метод, предоставляемый `SetHandler`, компилятору, который не создает записи оптимальным образом и который хотите оптимизировать сохраненных записей.</span><span class="sxs-lookup"><span data-stu-id="a8ab5-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="a8ab5-109">Если метод обратного вызова не предоставляется через `SetHandler`, будет выполняться без оптимизации на сохранить за исключением импортировать несколько областей, были объединены с помощью `IMapToken` на слияния для каждой области.</span><span class="sxs-lookup"><span data-stu-id="a8ab5-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8ab5-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a8ab5-110">Requirements</span></span>  
 <span data-ttu-id="a8ab5-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8ab5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8ab5-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a8ab5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8ab5-113">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8ab5-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8ab5-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8ab5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8ab5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a8ab5-115">See also</span></span>
- [<span data-ttu-id="a8ab5-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a8ab5-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a8ab5-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a8ab5-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
