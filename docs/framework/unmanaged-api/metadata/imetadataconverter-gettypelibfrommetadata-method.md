---
title: "Метод IMetaDataConverter::GetTypeLibFromMetaData"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1e7665eabf46d4bda822dcb41125ccfcee6d8516
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="09aec-102">Метод IMetaDataConverter::GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="09aec-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="09aec-103">Возвращает указатель на `ITypeLib` экземпляр, представляющий библиотеку типов с указанными именами библиотеки и модуль.</span><span class="sxs-lookup"><span data-stu-id="09aec-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09aec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09aec-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,   
    [in]  BSTR     strTlbName,   
    [out] ITypeLib **ppITL  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09aec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="09aec-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="09aec-106">[in] Имя модуля библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="09aec-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="09aec-107">[in] Имя библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="09aec-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="09aec-108">[out] Указатель на расположение, которая получает адрес `ITypeLib` экземпляр, представляющий библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="09aec-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09aec-109">Требования</span><span class="sxs-lookup"><span data-stu-id="09aec-109">Requirements</span></span>  
 <span data-ttu-id="09aec-110">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09aec-110">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09aec-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="09aec-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="09aec-112">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="09aec-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="09aec-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09aec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09aec-114">См. также</span><span class="sxs-lookup"><span data-stu-id="09aec-114">See Also</span></span>  
 [<span data-ttu-id="09aec-115">Интерфейс IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="09aec-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
