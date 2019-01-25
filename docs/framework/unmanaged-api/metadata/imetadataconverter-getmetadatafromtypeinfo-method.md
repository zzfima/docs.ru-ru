---
title: Метод IMetaDataConverter::GetMetaDataFromTypeInfo
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeInfo
helpviewer_keywords:
- GetMetaDataFromTypeInfo method [.NET Framework metadata]
- IMetaDataConverter::GetMetaDataFromTypeInfo method [.NET Framework metadata]
ms.assetid: d44484bb-23a3-49c3-9e46-69d0d9ab4f0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ae7007c4588724da7b3a67f924c981121d2c82bc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622225"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="8574b-102">Метод IMetaDataConverter::GetMetaDataFromTypeInfo</span><span class="sxs-lookup"><span data-stu-id="8574b-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>
<span data-ttu-id="8574b-103">Возвращает указатель на [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) экземпляр, представляющий подпись метаданных для библиотеки типов, который ссылается заданный `ITypeInfo` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="8574b-103">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8574b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8574b-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8574b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8574b-105">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="8574b-106">[in] Указатель на `ITypeInfo` объект, который ссылается на библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="8574b-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="8574b-107">[out] Указатель на расположение, которое получает адрес `IMetaDataImport` экземпляр, представляющий подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="8574b-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8574b-108">Требования</span><span class="sxs-lookup"><span data-stu-id="8574b-108">Requirements</span></span>  
 <span data-ttu-id="8574b-109">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8574b-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8574b-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8574b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8574b-111">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8574b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8574b-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8574b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8574b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8574b-113">See also</span></span>
- [<span data-ttu-id="8574b-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="8574b-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8574b-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="8574b-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
