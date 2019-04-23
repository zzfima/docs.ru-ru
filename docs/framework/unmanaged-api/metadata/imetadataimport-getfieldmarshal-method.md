---
title: Метод IMetaDataImport::GetFieldMarshal
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 35e780c330d0184d40bd99f34c3454f83075c1e0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139286"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="0c54d-102">Метод IMetaDataImport::GetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="0c54d-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="0c54d-103">Возвращает указатель на машинный неуправляемый тип поля, представленного маркер метаданных указанного поля.</span><span class="sxs-lookup"><span data-stu-id="0c54d-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c54d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c54d-104">Syntax</span></span>  
  
```  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c54d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0c54d-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="0c54d-106">[in] Токен метаданных, представляющий поле, чтобы получить взаимодействия сведения о маршалинге для.</span><span class="sxs-lookup"><span data-stu-id="0c54d-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="0c54d-107">[out] Указатель на собственный тип поля подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="0c54d-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="0c54d-108">[out] Размер в байтах `ppvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="0c54d-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c54d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="0c54d-109">Requirements</span></span>  
 <span data-ttu-id="0c54d-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c54d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c54d-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0c54d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c54d-112">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0c54d-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c54d-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c54d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c54d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0c54d-114">See also</span></span>

- [<span data-ttu-id="0c54d-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="0c54d-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0c54d-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="0c54d-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
