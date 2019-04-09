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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d3377617ddd6b82ad88d22f6ffda04b1d6ae837
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096128"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="d6e2b-102">Интерфейс IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="d6e2b-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="d6e2b-103">Предоставляет методы для сопоставления библиотек типов с их сигнатурами метаданных и для преобразования из одних в другие.</span><span class="sxs-lookup"><span data-stu-id="d6e2b-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d6e2b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d6e2b-104">Methods</span></span>  
  
|<span data-ttu-id="d6e2b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d6e2b-105">Method</span></span>|<span data-ttu-id="d6e2b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d6e2b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d6e2b-107">Метод GetMetaDataFromTypeInfo</span><span class="sxs-lookup"><span data-stu-id="d6e2b-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="d6e2b-108">Возвращает указатель на [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) экземпляр, представляющий подпись метаданных для библиотеки типов, который ссылается заданный `ITypeInfo` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d6e2b-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="d6e2b-109">Метод GetMetaDataFromTypeLib</span><span class="sxs-lookup"><span data-stu-id="d6e2b-109">GetMetaDataFromTypeLib Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="d6e2b-110">Возвращает указатель на `IMetaDataImport` экземпляр, представляющий подпись метаданных для библиотеки типов, представленного указанным `ITypeLib` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d6e2b-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="d6e2b-111">Метод GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="d6e2b-111">GetTypeLibFromMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="d6e2b-112">Возвращает указатель на `ITypeLib` экземпляр, представляющий библиотеку типов, с заданными именами модуля и библиотеки.</span><span class="sxs-lookup"><span data-stu-id="d6e2b-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d6e2b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d6e2b-113">Requirements</span></span>  
 <span data-ttu-id="d6e2b-114">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6e2b-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6e2b-115">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d6e2b-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d6e2b-116">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d6e2b-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="d6e2b-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d6e2b-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d6e2b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d6e2b-118">See also</span></span>

- [<span data-ttu-id="d6e2b-119">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="d6e2b-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="d6e2b-120">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d6e2b-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
