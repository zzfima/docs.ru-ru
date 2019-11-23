---
title: Интерфейс IMetaDataConverter
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
ms.openlocfilehash: b771b368c069a4577d266b47bfb4a5ee1935e48e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436268"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="5ad2a-102">Интерфейс IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="5ad2a-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="5ad2a-103">Предоставляет методы для сопоставления библиотек типов с их сигнатурами метаданных и для преобразования из одних в другие.</span><span class="sxs-lookup"><span data-stu-id="5ad2a-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5ad2a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="5ad2a-104">Methods</span></span>  
  
|<span data-ttu-id="5ad2a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="5ad2a-105">Method</span></span>|<span data-ttu-id="5ad2a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5ad2a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5ad2a-107">Метод GetMetaDataFromTypeInfo</span><span class="sxs-lookup"><span data-stu-id="5ad2a-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="5ad2a-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span><span class="sxs-lookup"><span data-stu-id="5ad2a-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="5ad2a-109">Метод GetMetaDataFromTypeLib</span><span class="sxs-lookup"><span data-stu-id="5ad2a-109">GetMetaDataFromTypeLib Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="5ad2a-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span><span class="sxs-lookup"><span data-stu-id="5ad2a-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="5ad2a-111">Метод GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="5ad2a-111">GetTypeLibFromMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="5ad2a-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span><span class="sxs-lookup"><span data-stu-id="5ad2a-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5ad2a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="5ad2a-113">Requirements</span></span>  
 <span data-ttu-id="5ad2a-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ad2a-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ad2a-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5ad2a-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ad2a-116">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5ad2a-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5ad2a-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ad2a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad2a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5ad2a-118">See also</span></span>

- [<span data-ttu-id="5ad2a-119">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="5ad2a-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="5ad2a-120">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5ad2a-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
