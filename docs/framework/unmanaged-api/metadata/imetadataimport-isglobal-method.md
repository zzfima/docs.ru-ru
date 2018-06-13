---
title: Метод IMetaDataImport::IsGlobal
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsGlobal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4156c3507ccbd21d59893c5e03e15fe9b7322e48
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447802"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="2355c-102">Метод IMetaDataImport::IsGlobal</span><span class="sxs-lookup"><span data-stu-id="2355c-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="2355c-103">Возвращает значение, указывающее на наличие глобальной области у поля, метода или типа, представленного заданным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="2355c-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2355c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2355c-104">Syntax</span></span>  
  
```  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2355c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2355c-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="2355c-106">[in] Токен метаданных, представляющий тип, поле или метод.</span><span class="sxs-lookup"><span data-stu-id="2355c-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="2355c-107">[out] 1, если объект имеет глобальную область; в противном случае — 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="2355c-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2355c-108">Требования</span><span class="sxs-lookup"><span data-stu-id="2355c-108">Requirements</span></span>  
 <span data-ttu-id="2355c-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2355c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2355c-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2355c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2355c-111">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2355c-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2355c-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2355c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2355c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="2355c-113">See Also</span></span>  
 [<span data-ttu-id="2355c-114">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="2355c-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="2355c-115">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="2355c-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
