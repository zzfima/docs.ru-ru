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
ms.openlocfilehash: e51cb1049737e6b325656057060a88123f69a9b4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493327"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="774e6-102">Метод IMetaDataEmit::SetParamProps</span><span class="sxs-lookup"><span data-stu-id="774e6-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="774e6-103">Задает или изменяет функции параметра метода, который определен с помощью предыдущего вызова [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="774e6-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="774e6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="774e6-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="774e6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="774e6-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="774e6-106">[in] Токен для параметра целевой объект.</span><span class="sxs-lookup"><span data-stu-id="774e6-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="774e6-107">[in] Имя параметра в формате Юникод.</span><span class="sxs-lookup"><span data-stu-id="774e6-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="774e6-108">[in] Флаги для параметра.</span><span class="sxs-lookup"><span data-stu-id="774e6-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="774e6-109">[in] ELEMENT_TYPE_ \* для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="774e6-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="774e6-110">[in] Постоянное значение для параметра.</span><span class="sxs-lookup"><span data-stu-id="774e6-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="774e6-111">[in] Размер в символах (Юникод) `pValue`.</span><span class="sxs-lookup"><span data-stu-id="774e6-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="774e6-112">Требования</span><span class="sxs-lookup"><span data-stu-id="774e6-112">Requirements</span></span>  
 <span data-ttu-id="774e6-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="774e6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="774e6-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="774e6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="774e6-115">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="774e6-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="774e6-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="774e6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="774e6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="774e6-117">See also</span></span>
- [<span data-ttu-id="774e6-118">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="774e6-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="774e6-119">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="774e6-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
