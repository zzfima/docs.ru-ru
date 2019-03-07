---
title: Метод IMetaDataConverter::GetTypeLibFromMetaData
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9ab1d39ddb53e08e6fd36016f544162e2b11edb0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472074"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="814c9-102">Метод IMetaDataConverter::GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="814c9-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="814c9-103">Возвращает указатель на `ITypeLib` экземпляр, представляющий библиотеку типов, с заданными именами библиотеки и модуль.</span><span class="sxs-lookup"><span data-stu-id="814c9-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="814c9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="814c9-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,   
    [in]  BSTR     strTlbName,   
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="814c9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="814c9-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="814c9-106">[in] Имя модуля библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="814c9-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="814c9-107">[in] Имя библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="814c9-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="814c9-108">[out] Указатель на расположение, которое получает адрес `ITypeLib` экземпляр, представляющий библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="814c9-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="814c9-109">Требования</span><span class="sxs-lookup"><span data-stu-id="814c9-109">Requirements</span></span>  
 <span data-ttu-id="814c9-110">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="814c9-110">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="814c9-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="814c9-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="814c9-112">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="814c9-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="814c9-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="814c9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="814c9-114">См. также</span><span class="sxs-lookup"><span data-stu-id="814c9-114">See also</span></span>
- [<span data-ttu-id="814c9-115">Интерфейс IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="814c9-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
