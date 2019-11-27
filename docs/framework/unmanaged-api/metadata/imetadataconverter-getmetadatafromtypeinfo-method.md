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
ms.openlocfilehash: df7be11e8f275824fca658a9604178e7cf28e3ce
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436291"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="1d19a-102">Метод IMetaDataConverter::GetMetaDataFromTypeInfo</span><span class="sxs-lookup"><span data-stu-id="1d19a-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>
<span data-ttu-id="1d19a-103">Возвращает указатель на экземпляр [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) , представляющий сигнатуру метаданных библиотеки типов, на которую ссылается указанный экземпляр `ITypeInfo`.</span><span class="sxs-lookup"><span data-stu-id="1d19a-103">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d19a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d19a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d19a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1d19a-105">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="1d19a-106">окне Указатель на объект `ITypeInfo`, который ссылается на библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="1d19a-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="1d19a-107">заполняет Указатель на расположение, которое получает адрес экземпляра `IMetaDataImport`, представляющего сигнатуру метаданных.</span><span class="sxs-lookup"><span data-stu-id="1d19a-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d19a-108">Требования</span><span class="sxs-lookup"><span data-stu-id="1d19a-108">Requirements</span></span>  
 <span data-ttu-id="1d19a-109">**Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d19a-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d19a-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="1d19a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d19a-111">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1d19a-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d19a-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d19a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d19a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="1d19a-113">See also</span></span>

- [<span data-ttu-id="1d19a-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="1d19a-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1d19a-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="1d19a-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
