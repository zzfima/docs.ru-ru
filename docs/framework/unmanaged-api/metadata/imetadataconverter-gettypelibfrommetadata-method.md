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
ms.openlocfilehash: c0943971dc4858e2dce4d977f6f906b26f8ad51e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59231018"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="31e52-102">Метод IMetaDataConverter::GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="31e52-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="31e52-103">Возвращает указатель на `ITypeLib` экземпляр, представляющий библиотеку типов, с заданными именами библиотеки и модуль.</span><span class="sxs-lookup"><span data-stu-id="31e52-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31e52-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31e52-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,   
    [in]  BSTR     strTlbName,   
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31e52-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="31e52-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="31e52-106">[in] Имя модуля библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="31e52-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="31e52-107">[in] Имя библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="31e52-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="31e52-108">[out] Указатель на расположение, которое получает адрес `ITypeLib` экземпляр, представляющий библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="31e52-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31e52-109">Требования</span><span class="sxs-lookup"><span data-stu-id="31e52-109">Requirements</span></span>  
 <span data-ttu-id="31e52-110">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31e52-110">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31e52-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="31e52-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="31e52-112">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="31e52-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="31e52-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31e52-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31e52-114">См. также</span><span class="sxs-lookup"><span data-stu-id="31e52-114">See also</span></span>

- [<span data-ttu-id="31e52-115">Интерфейс IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="31e52-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
