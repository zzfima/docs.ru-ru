---
title: Метод IMetaDataEmit::SetCustomAttributeValue
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2c6e97327497993372f17e1c352ca6a8e5b2eac9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493509"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="a5b33-102">Метод IMetaDataEmit::SetCustomAttributeValue</span><span class="sxs-lookup"><span data-stu-id="a5b33-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="a5b33-103">Задает или обновляет значение настраиваемого атрибута определен во время предыдущего вызова к [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="a5b33-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5b33-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5b33-104">Syntax</span></span>  
  
```  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5b33-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5b33-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="a5b33-106">[in] Токен целевого пользовательского атрибута.</span><span class="sxs-lookup"><span data-stu-id="a5b33-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="a5b33-107">[in] Указатель на массив, содержащий пользовательский атрибут.</span><span class="sxs-lookup"><span data-stu-id="a5b33-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="a5b33-108">[in] Размер в байтах, настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="a5b33-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5b33-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a5b33-109">Requirements</span></span>  
 <span data-ttu-id="a5b33-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5b33-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5b33-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a5b33-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5b33-112">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a5b33-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5b33-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5b33-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b33-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a5b33-114">See also</span></span>
- [<span data-ttu-id="a5b33-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a5b33-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a5b33-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a5b33-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
