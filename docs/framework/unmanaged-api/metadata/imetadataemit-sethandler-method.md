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
ms.openlocfilehash: 375c4b2cece0bdfd763ae383c5412c9e25614baf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177545"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="7c880-102">Метод IMetaDataEmit::SetHandler</span><span class="sxs-lookup"><span data-stu-id="7c880-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="7c880-103">Устанавливает метод, указанный `IUnknown` указателем, в качестве обратного вызова уведомлений для рекарт маркеров.</span><span class="sxs-lookup"><span data-stu-id="7c880-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c880-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c880-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c880-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7c880-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="7c880-106">(в) Обработчик для регистрации.</span><span class="sxs-lookup"><span data-stu-id="7c880-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c880-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="7c880-107">Remarks</span></span>  
 <span data-ttu-id="7c880-108">Движок метаданных отправляет уведомления с помощью `SetHandler`предоставленного метода компиляторы, которые не генерируют записи оптимизированным способом и которые хотели бы оптимизировать сохраненные записи.</span><span class="sxs-lookup"><span data-stu-id="7c880-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="7c880-109">Если метод обратного откаивается не через, `SetHandler`не будет выполнена оптимизация при `IMapToken` сохранении, за исключением случаев, когда несколько областей импорта были объединены с использованием на слиянии для каждой области.</span><span class="sxs-lookup"><span data-stu-id="7c880-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c880-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7c880-110">Requirements</span></span>  
 <span data-ttu-id="7c880-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c880-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c880-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7c880-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c880-113">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c880-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c880-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c880-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c880-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7c880-115">See also</span></span>

- [<span data-ttu-id="7c880-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="7c880-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7c880-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="7c880-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
