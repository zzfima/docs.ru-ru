---
title: Метод IMetaDataConverter::GetMetaDataFromTypeLib
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeLib
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib
helpviewer_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib method [.NET Framework metadata]
- GetMetaDataFromTypeLib method [.NET Framework metadata]
ms.assetid: 97dc3a56-adfa-431f-889e-06a35ac84d51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cdc1b0de9795a000ee680df880c73acc4f711db2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145331"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="58e06-102">Метод IMetaDataConverter::GetMetaDataFromTypeLib</span><span class="sxs-lookup"><span data-stu-id="58e06-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="58e06-103">Получает указатель интерфейса на [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) экземпляр, представляющий подпись метаданных для библиотеки типов, представленного указанным `ITypeLib` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="58e06-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58e06-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58e06-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,   
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58e06-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="58e06-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="58e06-106">[in] Указатель на `ITypeLib` , представляющий библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="58e06-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="58e06-107">[out] Указатель на расположение, которое получает адрес `IMetaDataImport` экземпляр, представляющий подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="58e06-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58e06-108">Требования</span><span class="sxs-lookup"><span data-stu-id="58e06-108">Requirements</span></span>  
 <span data-ttu-id="58e06-109">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58e06-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58e06-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="58e06-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58e06-111">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="58e06-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="58e06-112">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="58e06-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="58e06-113">См. также</span><span class="sxs-lookup"><span data-stu-id="58e06-113">See also</span></span>

- [<span data-ttu-id="58e06-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="58e06-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="58e06-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="58e06-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
