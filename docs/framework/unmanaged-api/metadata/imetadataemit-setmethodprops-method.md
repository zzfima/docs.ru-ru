---
title: Метод IMetaDataEmit::SetMethodProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 534afdd5990435c6b4db5ef8ea27a8065b199496
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050016"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="e8cff-102">Метод IMetaDataEmit::SetMethodProps</span><span class="sxs-lookup"><span data-stu-id="e8cff-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="e8cff-103">Задает или обновляет функцию, хранимую в указанного относительного виртуального адреса, определенные с помощью предыдущего вызова метода [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="e8cff-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8cff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8cff-104">Syntax</span></span>  
  
```  
HRESULT SetMethodProps (   
    [in]  mdMethodDef md,   
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,   
    [in]  DWORD       dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8cff-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e8cff-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="e8cff-106">[in] Токен, метод должен быть изменен.</span><span class="sxs-lookup"><span data-stu-id="e8cff-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="e8cff-107">[in] Атрибуты элементов.</span><span class="sxs-lookup"><span data-stu-id="e8cff-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="e8cff-108">[in] Адрес кода.</span><span class="sxs-lookup"><span data-stu-id="e8cff-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="e8cff-109">[in] Флаги реализации метода.</span><span class="sxs-lookup"><span data-stu-id="e8cff-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8cff-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e8cff-110">Requirements</span></span>  
 <span data-ttu-id="e8cff-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8cff-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8cff-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e8cff-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e8cff-113">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e8cff-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8cff-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8cff-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8cff-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e8cff-115">See also</span></span>

- [<span data-ttu-id="e8cff-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e8cff-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e8cff-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e8cff-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
