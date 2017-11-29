---
title: "Метод IMetaDataEmit::DefineParam"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineParam
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5abe9cf0385a42645468bf58c2f81223ac4eeead
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="92238-102">Метод IMetaDataEmit::DefineParam</span><span class="sxs-lookup"><span data-stu-id="92238-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="92238-103">Создает определение параметра с заданной подписью для метода, который ссылается указанный токен и получает маркер для данного определения параметра.</span><span class="sxs-lookup"><span data-stu-id="92238-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92238-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92238-104">Syntax</span></span>  
  
```  
HRESULT DefineParam (  
    [in]  mdMethodDef md,   
    [in]  ULONG       ulParamSeq,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,   
    [out] mdParamDef  *ppd   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92238-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="92238-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="92238-106">[in] Токен для метода, параметры которого определяется.</span><span class="sxs-lookup"><span data-stu-id="92238-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="92238-107">[in] Порядковый номер параметра.</span><span class="sxs-lookup"><span data-stu-id="92238-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="92238-108">[in] Имя параметра в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="92238-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="92238-109">[in] Флаги для параметра.</span><span class="sxs-lookup"><span data-stu-id="92238-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="92238-110">Это битовая маска `CorParamAttr` значения.</span><span class="sxs-lookup"><span data-stu-id="92238-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="92238-111">[in] `ELEMENT_TYPE_`  *\**  для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="92238-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="92238-112">[in] Постоянное значение для параметра.</span><span class="sxs-lookup"><span data-stu-id="92238-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="92238-113">[in] Размер в символы Юникода из `pValue`.</span><span class="sxs-lookup"><span data-stu-id="92238-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="92238-114">[out] `mdParamDef` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="92238-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92238-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="92238-115">Remarks</span></span>  
 <span data-ttu-id="92238-116">Последовательность значений элементов в `ulParamSeq` начинаются с 1 для параметров.</span><span class="sxs-lookup"><span data-stu-id="92238-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="92238-117">Возвращаемое значение имеет порядковый номер 0.</span><span class="sxs-lookup"><span data-stu-id="92238-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92238-118">Требования</span><span class="sxs-lookup"><span data-stu-id="92238-118">Requirements</span></span>  
 <span data-ttu-id="92238-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92238-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92238-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="92238-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92238-121">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="92238-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92238-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92238-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92238-123">См. также</span><span class="sxs-lookup"><span data-stu-id="92238-123">See Also</span></span>  
 [<span data-ttu-id="92238-124">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="92238-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="92238-125">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="92238-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
