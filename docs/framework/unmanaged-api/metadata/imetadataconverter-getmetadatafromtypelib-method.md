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
ms.openlocfilehash: a390187e5fd73824f2fad026365371642235a6f9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777878"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="f1532-102">Метод IMetaDataConverter::GetMetaDataFromTypeLib</span><span class="sxs-lookup"><span data-stu-id="f1532-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="f1532-103">Получает указатель интерфейса на [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) экземпляр, представляющий подпись метаданных для библиотеки типов, представленного указанным `ITypeLib` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f1532-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1532-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1532-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,   
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1532-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f1532-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="f1532-106">[in] Указатель на `ITypeLib` , представляющий библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="f1532-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="f1532-107">[out] Указатель на расположение, которое получает адрес `IMetaDataImport` экземпляр, представляющий подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="f1532-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1532-108">Требования</span><span class="sxs-lookup"><span data-stu-id="f1532-108">Requirements</span></span>  
 <span data-ttu-id="f1532-109">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1532-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1532-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f1532-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1532-111">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f1532-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f1532-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1532-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1532-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f1532-113">See also</span></span>

- [<span data-ttu-id="f1532-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f1532-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f1532-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f1532-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
