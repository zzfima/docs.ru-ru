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
ms.openlocfilehash: 6391e819d53c3ed8f0d596b15c4a2bb268f72fd5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436282"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="88794-102">Метод IMetaDataConverter::GetMetaDataFromTypeLib</span><span class="sxs-lookup"><span data-stu-id="88794-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="88794-103">Возвращает указатель интерфейса на экземпляр [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) , представляющий сигнатуру метаданных библиотеки типов, представленной указанным экземпляром `ITypeLib`.</span><span class="sxs-lookup"><span data-stu-id="88794-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88794-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88794-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,   
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88794-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="88794-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="88794-106">окне Указатель на объект `ITypeLib`, представляющий библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="88794-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="88794-107">заполняет Указатель на расположение, которое получает адрес экземпляра `IMetaDataImport`, представляющего сигнатуру метаданных.</span><span class="sxs-lookup"><span data-stu-id="88794-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88794-108">Требования</span><span class="sxs-lookup"><span data-stu-id="88794-108">Requirements</span></span>  
 <span data-ttu-id="88794-109">**Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88794-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88794-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="88794-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="88794-111">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="88794-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="88794-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88794-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88794-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="88794-113">See also</span></span>

- [<span data-ttu-id="88794-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="88794-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="88794-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="88794-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
