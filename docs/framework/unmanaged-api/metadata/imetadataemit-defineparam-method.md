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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d64a1ef21cd4fa4224609c7cd415c1611313769
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777545"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="f3b52-102">Метод IMetaDataEmit::DefineParam</span><span class="sxs-lookup"><span data-stu-id="f3b52-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="f3b52-103">Создает определение параметра с указанной сигнатурой метода, который ссылается указанный токен и получает маркер для данного определения параметра.</span><span class="sxs-lookup"><span data-stu-id="f3b52-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3b52-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3b52-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f3b52-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3b52-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="f3b52-106">[in] Токен для метода, параметр которого определяется.</span><span class="sxs-lookup"><span data-stu-id="f3b52-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="f3b52-107">[in] Порядковый номер параметра.</span><span class="sxs-lookup"><span data-stu-id="f3b52-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="f3b52-108">[in] Имя параметра в формате Юникод.</span><span class="sxs-lookup"><span data-stu-id="f3b52-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="f3b52-109">[in] Флаги для параметра.</span><span class="sxs-lookup"><span data-stu-id="f3b52-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="f3b52-110">Это битовая маска `CorParamAttr` значения.</span><span class="sxs-lookup"><span data-stu-id="f3b52-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="f3b52-111">[in] `ELEMENT_TYPE_` *\** для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="f3b52-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="f3b52-112">[in] Постоянное значение для параметра.</span><span class="sxs-lookup"><span data-stu-id="f3b52-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="f3b52-113">[in] Размер в символы Юникода из `pValue`.</span><span class="sxs-lookup"><span data-stu-id="f3b52-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="f3b52-114">[out] `mdParamDef` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="f3b52-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3b52-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3b52-115">Remarks</span></span>  
 <span data-ttu-id="f3b52-116">Последовательность значений элементов в `ulParamSeq` начинаются с 1 для параметров.</span><span class="sxs-lookup"><span data-stu-id="f3b52-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="f3b52-117">Возвращаемое значение имеет порядковый номер 0.</span><span class="sxs-lookup"><span data-stu-id="f3b52-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3b52-118">Требования</span><span class="sxs-lookup"><span data-stu-id="f3b52-118">Requirements</span></span>  
 <span data-ttu-id="f3b52-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3b52-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3b52-120">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f3b52-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f3b52-121">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f3b52-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3b52-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3b52-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3b52-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f3b52-123">See also</span></span>

- [<span data-ttu-id="f3b52-124">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f3b52-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f3b52-125">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f3b52-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
