---
title: "Метод IMetaDataImport::GetNameFromToken"
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
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: baa0c0e78f7912561b432effd2bf5503e0f06ae7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="6becb-102">Метод IMetaDataImport::GetNameFromToken</span><span class="sxs-lookup"><span data-stu-id="6becb-102">IMetaDataImport::GetNameFromToken Method</span></span>
<span data-ttu-id="6becb-103">Возвращает имя объекта, на который ссылается указанный токен метаданных, в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="6becb-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="6becb-104">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="6becb-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6becb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6becb-105">Syntax</span></span>  
  
```  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6becb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6becb-106">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="6becb-107">[in] Токен, представляющий имя возвращаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="6becb-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="6becb-108">[out] Указатель на имя объекта в куче UTF-8.</span><span class="sxs-lookup"><span data-stu-id="6becb-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6becb-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="6becb-109">Remarks</span></span>  
 <span data-ttu-id="6becb-110">`GetNameFromToken` устарел.</span><span class="sxs-lookup"><span data-stu-id="6becb-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="6becb-111">Кроме того, вызовите метод, чтобы получить свойства конкретного типа маркера, таких как `GetFieldProps` для поля или `GetMethodProps` для метода.</span><span class="sxs-lookup"><span data-stu-id="6becb-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6becb-112">Требования</span><span class="sxs-lookup"><span data-stu-id="6becb-112">Requirements</span></span>  
 <span data-ttu-id="6becb-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6becb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6becb-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6becb-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6becb-115">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6becb-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6becb-116">**Версии платформы .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="6becb-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6becb-117">См. также</span><span class="sxs-lookup"><span data-stu-id="6becb-117">See Also</span></span>  
 [<span data-ttu-id="6becb-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6becb-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="6becb-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6becb-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
