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
ms.openlocfilehash: 6737275fb77e6f177832eb1d96214c37942bcd22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442152"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="635d6-102">Метод IMetaDataEmit::SetHandler</span><span class="sxs-lookup"><span data-stu-id="635d6-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="635d6-103">Задает метод, на который ссылается указанный указатель `IUnknown` в качестве обратного вызова уведомления для повторного сопоставления токенов.</span><span class="sxs-lookup"><span data-stu-id="635d6-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="635d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="635d6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="635d6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="635d6-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="635d6-106">окне Регистрируемый обработчик.</span><span class="sxs-lookup"><span data-stu-id="635d6-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="635d6-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="635d6-107">Remarks</span></span>  
 <span data-ttu-id="635d6-108">Обработчик метаданных отправляет уведомление с помощью метода, предоставляемого `SetHandler`, компиляторам, которые не создают записи оптимизированным образом и которым требуется оптимизировать сохраненные записи.</span><span class="sxs-lookup"><span data-stu-id="635d6-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="635d6-109">Если метод обратного вызова не предоставляется через `SetHandler`, оптимизация не будет выполняться при сохранении, за исключением случаев, когда несколько областей импорта были объединены с помощью `IMapToken` для каждой области слияния.</span><span class="sxs-lookup"><span data-stu-id="635d6-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="635d6-110">Требования</span><span class="sxs-lookup"><span data-stu-id="635d6-110">Requirements</span></span>  
 <span data-ttu-id="635d6-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="635d6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="635d6-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="635d6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="635d6-113">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="635d6-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="635d6-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="635d6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="635d6-115">См. также</span><span class="sxs-lookup"><span data-stu-id="635d6-115">See also</span></span>

- [<span data-ttu-id="635d6-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="635d6-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="635d6-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="635d6-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
