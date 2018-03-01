---
title: "Метод IMetaDataImport::GetFieldMarshal"
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
- IMetaDataImport.GetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7a41b766dc377a62ad7d1d3ee7ebe5632a81cce2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="2b455-102">Метод IMetaDataImport::GetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="2b455-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="2b455-103">Возвращает указатель на машинный неуправляемый тип поля, представленного токен метаданных указанного поля.</span><span class="sxs-lookup"><span data-stu-id="2b455-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b455-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b455-104">Syntax</span></span>  
  
```  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b455-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b455-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="2b455-106">[in] Токен метаданных, представляющий взаимодействия сведения о маршалинге для поля.</span><span class="sxs-lookup"><span data-stu-id="2b455-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="2b455-107">[out] Указатель на собственный тип поля подписи метаданных.</span><span class="sxs-lookup"><span data-stu-id="2b455-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="2b455-108">[out] Размер в байтах `ppvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="2b455-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b455-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2b455-109">Requirements</span></span>  
 <span data-ttu-id="2b455-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b455-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b455-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2b455-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2b455-112">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2b455-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2b455-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b455-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b455-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2b455-114">See Also</span></span>  
 [<span data-ttu-id="2b455-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="2b455-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="2b455-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="2b455-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
