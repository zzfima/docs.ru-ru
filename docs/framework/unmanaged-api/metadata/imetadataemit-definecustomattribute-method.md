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
ms.openlocfilehash: a11e9919dc1338c4b67c3c4b0f082e330c29d9eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445086"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="0c769-102">Метод IMetaDataEmit::DefineCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="0c769-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="0c769-103">Создает определение настраиваемого атрибута с заданной подписью метаданных, подключен к указанного объекта и возвращает маркер для этого определения настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="0c769-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c769-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c769-104">Syntax</span></span>  
  
```  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c769-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0c769-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="0c769-106">[in] Токен для владельца элемента.</span><span class="sxs-lookup"><span data-stu-id="0c769-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="0c769-107">[in] Токен, который определяет настраиваемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="0c769-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="0c769-108">[in] Указатель на пользовательского атрибута.</span><span class="sxs-lookup"><span data-stu-id="0c769-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="0c769-109">[in] Число байт в `pCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="0c769-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="0c769-110">[out] `mdCustomAttribute` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="0c769-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c769-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0c769-111">Requirements</span></span>  
 <span data-ttu-id="0c769-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c769-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c769-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0c769-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c769-114">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0c769-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c769-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c769-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c769-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0c769-116">See Also</span></span>  
 [<span data-ttu-id="0c769-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="0c769-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0c769-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="0c769-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
