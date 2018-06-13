---
title: Метод IMetaDataEmit::SetParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 61688ed5201a1bb6721c4db70b380c7b8373c2e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446445"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="bc6b2-102">Метод IMetaDataEmit::SetParamProps</span><span class="sxs-lookup"><span data-stu-id="bc6b2-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="bc6b2-103">Задает или изменяет функции параметра метода, который был определен во время предыдущего вызова для [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="bc6b2-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc6b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc6b2-104">Syntax</span></span>  
  
```  
HRESULT SetParamProps (   
    [in]  mdParamDef  pd,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc6b2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bc6b2-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="bc6b2-106">[in] Маркер целевым параметром.</span><span class="sxs-lookup"><span data-stu-id="bc6b2-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="bc6b2-107">[in] Имя параметра в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="bc6b2-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="bc6b2-108">[in] Флаги для параметра.</span><span class="sxs-lookup"><span data-stu-id="bc6b2-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="bc6b2-109">[in] ELEMENT_TYPE_ \* для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="bc6b2-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="bc6b2-110">[in] Постоянное значение для параметра.</span><span class="sxs-lookup"><span data-stu-id="bc6b2-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="bc6b2-111">[in] Размер в символах (Юникод) `pValue`.</span><span class="sxs-lookup"><span data-stu-id="bc6b2-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc6b2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bc6b2-112">Requirements</span></span>  
 <span data-ttu-id="bc6b2-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc6b2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc6b2-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bc6b2-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc6b2-115">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bc6b2-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc6b2-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc6b2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc6b2-117">См. также</span><span class="sxs-lookup"><span data-stu-id="bc6b2-117">See Also</span></span>  
 [<span data-ttu-id="bc6b2-118">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="bc6b2-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="bc6b2-119">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="bc6b2-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
