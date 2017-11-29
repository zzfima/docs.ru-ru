---
title: "Интерфейс IMetaDataConverter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataConverter
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataConverter
helpviewer_keywords: IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f551a774a860f595cc90a7cca9eee2c726ef50ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="7dcec-102">Интерфейс IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="7dcec-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="7dcec-103">Предоставляет методы для сопоставления библиотек типов с их сигнатурами метаданных и для преобразования из одних в другие.</span><span class="sxs-lookup"><span data-stu-id="7dcec-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7dcec-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7dcec-104">Methods</span></span>  
  
|<span data-ttu-id="7dcec-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7dcec-105">Method</span></span>|<span data-ttu-id="7dcec-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7dcec-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7dcec-107">Метод GetMetaDataFromTypeInfo</span><span class="sxs-lookup"><span data-stu-id="7dcec-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="7dcec-108">Возвращает указатель на [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) экземпляр, представляющий подпись метаданных для библиотеки типов, который ссылается заданный дескриптор `ITypeInfo` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="7dcec-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="7dcec-109">Метод GetMetaDataFromTypeLib</span><span class="sxs-lookup"><span data-stu-id="7dcec-109">GetMetaDataFromTypeLib Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="7dcec-110">Возвращает указатель на `IMetaDataImport` экземпляр, представляющий подпись метаданных для библиотеки типов, представленный указанным `ITypeLib` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="7dcec-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="7dcec-111">Метод GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="7dcec-111">GetTypeLibFromMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="7dcec-112">Возвращает указатель на `ITypeLib` экземпляр, представляющий библиотеку типов с указанными именами модуль и библиотеки.</span><span class="sxs-lookup"><span data-stu-id="7dcec-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7dcec-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7dcec-113">Requirements</span></span>  
 <span data-ttu-id="7dcec-114">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dcec-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dcec-115">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7dcec-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7dcec-116">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7dcec-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7dcec-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dcec-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dcec-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7dcec-118">See Also</span></span>  
 [<span data-ttu-id="7dcec-119">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="7dcec-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="7dcec-120">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="7dcec-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
