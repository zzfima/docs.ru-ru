---
title: "Метод IMetaDataEmit::DefineCustomAttribute"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineCustomAttribute
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1c4c00480571b4160d7442aeafea088fe8d04ba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="b9b10-102">Метод IMetaDataEmit::DefineCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="b9b10-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="b9b10-103">Создает определение настраиваемого атрибута с заданной подписью метаданных, подключен к указанного объекта и возвращает маркер для этого определения настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="b9b10-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9b10-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9b10-104">Syntax</span></span>  
  
```  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9b10-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9b10-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="b9b10-106">[in] Токен для владельца элемента.</span><span class="sxs-lookup"><span data-stu-id="b9b10-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="b9b10-107">[in] Токен, который определяет настраиваемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="b9b10-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="b9b10-108">[in] Указатель на пользовательского атрибута.</span><span class="sxs-lookup"><span data-stu-id="b9b10-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="b9b10-109">[in] Число байт в `pCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="b9b10-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="b9b10-110">[out] `mdCustomAttribute` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="b9b10-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9b10-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b9b10-111">Requirements</span></span>  
 <span data-ttu-id="b9b10-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9b10-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9b10-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b9b10-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9b10-114">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9b10-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9b10-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9b10-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9b10-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b9b10-116">See Also</span></span>  
 [<span data-ttu-id="b9b10-117">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b9b10-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="b9b10-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b9b10-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
