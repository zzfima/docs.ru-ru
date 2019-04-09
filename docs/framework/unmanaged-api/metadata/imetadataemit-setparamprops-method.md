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
ms.openlocfilehash: 6b7cfba90edab44a0053fdfc759417ee7f074401
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132038"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="6ab8e-102">Метод IMetaDataEmit::SetParamProps</span><span class="sxs-lookup"><span data-stu-id="6ab8e-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="6ab8e-103">Задает или изменяет функции параметра метода, который определен с помощью предыдущего вызова [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="6ab8e-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ab8e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ab8e-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="6ab8e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6ab8e-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="6ab8e-106">[in] Токен для параметра целевой объект.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="6ab8e-107">[in] Имя параметра в формате Юникод.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="6ab8e-108">[in] Флаги для параметра.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="6ab8e-109">[in] ELEMENT_TYPE_ \* для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="6ab8e-110">[in] Постоянное значение для параметра.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="6ab8e-111">[in] Размер в символах (Юникод) `pValue`.</span><span class="sxs-lookup"><span data-stu-id="6ab8e-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ab8e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="6ab8e-112">Requirements</span></span>  
 <span data-ttu-id="6ab8e-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ab8e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ab8e-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6ab8e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6ab8e-115">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6ab8e-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6ab8e-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6ab8e-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6ab8e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="6ab8e-117">See also</span></span>

- [<span data-ttu-id="6ab8e-118">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="6ab8e-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6ab8e-119">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="6ab8e-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
