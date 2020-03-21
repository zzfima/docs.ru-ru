---
title: Метод IMetaDataEmit::DefineParam
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
ms.openlocfilehash: 2807458549db02598ba05f2aa80fa6ea6fbc5a13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177691"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="96541-102">Метод IMetaDataEmit::DefineParam</span><span class="sxs-lookup"><span data-stu-id="96541-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="96541-103">Создает определение параметров с указанной подписью для метода, на который ссылается указанный маркер, и получает маркер для определения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="96541-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96541-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96541-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="96541-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="96541-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="96541-106">(в) Токен для метода, параметр которого определяется.</span><span class="sxs-lookup"><span data-stu-id="96541-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="96541-107">(в) Номер последовательности параметра.</span><span class="sxs-lookup"><span data-stu-id="96541-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="96541-108">(в) Название параметра в Unicode.</span><span class="sxs-lookup"><span data-stu-id="96541-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="96541-109">(в) Флаги для параметра.</span><span class="sxs-lookup"><span data-stu-id="96541-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="96541-110">Это битмаска ценностей. `CorParamAttr`</span><span class="sxs-lookup"><span data-stu-id="96541-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="96541-111">(в) `ELEMENT_TYPE_` для постоянного *\** значения.</span><span class="sxs-lookup"><span data-stu-id="96541-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="96541-112">(в) Постоянное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="96541-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="96541-113">(в) Размер, в unicode символов, из `pValue`.</span><span class="sxs-lookup"><span data-stu-id="96541-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="96541-114">(ваут) Назначенный `mdParamDef` маркер.</span><span class="sxs-lookup"><span data-stu-id="96541-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96541-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="96541-115">Remarks</span></span>  
 <span data-ttu-id="96541-116">Значения последовательности `ulParamSeq` начинаются с 1 для параметров.</span><span class="sxs-lookup"><span data-stu-id="96541-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="96541-117">Значение возврата имеет число последовательности 0.</span><span class="sxs-lookup"><span data-stu-id="96541-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96541-118">Требования</span><span class="sxs-lookup"><span data-stu-id="96541-118">Requirements</span></span>  
 <span data-ttu-id="96541-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96541-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96541-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="96541-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="96541-121">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="96541-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96541-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96541-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96541-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="96541-123">See also</span></span>

- [<span data-ttu-id="96541-124">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="96541-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="96541-125">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="96541-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
