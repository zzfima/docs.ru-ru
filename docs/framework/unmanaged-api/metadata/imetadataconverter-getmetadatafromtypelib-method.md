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
ms.openlocfilehash: 09a1605deda5b51be604c3b8f0c69fa5adcf9dc0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175958"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="82e7f-102">Метод IMetaDataConverter::GetMetaDataFromTypeLib</span><span class="sxs-lookup"><span data-stu-id="82e7f-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="82e7f-103">Получает указатель интерфейса в экземпляр [IMetaDataImport,](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) представляющий подпись метаданных библиотеки типа, представленную указанным `ITypeLib` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="82e7f-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82e7f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82e7f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82e7f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="82e7f-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="82e7f-106">(в) Указатель на `ITypeLib` объект, представляющий библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="82e7f-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="82e7f-107">(ваут) Указатель на место, которое `IMetaDataImport` получает адрес экземпляра, представляющего подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="82e7f-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82e7f-108">Требования</span><span class="sxs-lookup"><span data-stu-id="82e7f-108">Requirements</span></span>  
 <span data-ttu-id="82e7f-109">**Платформа:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82e7f-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82e7f-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="82e7f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="82e7f-111">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="82e7f-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="82e7f-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82e7f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82e7f-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="82e7f-113">See also</span></span>

- [<span data-ttu-id="82e7f-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="82e7f-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="82e7f-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="82e7f-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
