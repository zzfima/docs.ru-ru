---
title: Метод IMetaDataEmit::DefineCustomAttribute
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: adf3c74526bbf2b8e740f505ab6f4243cd799041
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474583"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="da130-102">Метод IMetaDataEmit::DefineCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="da130-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="da130-103">Создает определение настраиваемого атрибута с заданной подписью метаданных, должны быть присоединены к заданного объекта и получает маркер для этого определения настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="da130-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da130-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da130-104">Syntax</span></span>  
  
```  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da130-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="da130-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="da130-106">[in] Токен для владельца элемента.</span><span class="sxs-lookup"><span data-stu-id="da130-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="da130-107">[in] Токен, который определяет настраиваемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="da130-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="da130-108">[in] Указатель на пользовательском атрибуте.</span><span class="sxs-lookup"><span data-stu-id="da130-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="da130-109">[in] Число байт в `pCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="da130-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="da130-110">[out] `mdCustomAttribute` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="da130-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da130-111">Требования</span><span class="sxs-lookup"><span data-stu-id="da130-111">Requirements</span></span>  
 <span data-ttu-id="da130-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da130-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da130-113">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="da130-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da130-114">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da130-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da130-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da130-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da130-116">См. также</span><span class="sxs-lookup"><span data-stu-id="da130-116">See also</span></span>
- [<span data-ttu-id="da130-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="da130-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="da130-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="da130-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
