---
title: Метод IMetaDataImport::GetParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05ac8efed8c0a905d2cfad433348a99fe578eeae
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153183"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="c2c95-102">Метод IMetaDataImport::GetParamProps</span><span class="sxs-lookup"><span data-stu-id="c2c95-102">IMetaDataImport::GetParamProps Method</span></span>
<span data-ttu-id="c2c95-103">Возвращает значения метаданных для параметра, на который ссылается указанный токен ParamDef.</span><span class="sxs-lookup"><span data-stu-id="c2c95-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2c95-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2c95-104">Syntax</span></span>  
  
```  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2c95-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2c95-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="c2c95-106">[in] Токен ParamDef, который представляет метаданные для возвращаемого параметра.</span><span class="sxs-lookup"><span data-stu-id="c2c95-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="c2c95-107">[out] Указатель на токен MethodDef, предоставляющий метод, который принимает параметр.</span><span class="sxs-lookup"><span data-stu-id="c2c95-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="c2c95-108">[out] Порядковая позиция параметра в списке аргументов метода.</span><span class="sxs-lookup"><span data-stu-id="c2c95-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="c2c95-109">[out] Буфер для хранения имени параметра.</span><span class="sxs-lookup"><span data-stu-id="c2c95-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c2c95-110">[in] Запрошенный размер в расширенных символах `szName`.</span><span class="sxs-lookup"><span data-stu-id="c2c95-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="c2c95-111">[out] Возвращаемый размер в расширенных символах `szName`.</span><span class="sxs-lookup"><span data-stu-id="c2c95-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="c2c95-112">[out] Указатель на любой атрибут флаги, связанные с параметром.</span><span class="sxs-lookup"><span data-stu-id="c2c95-112">[out] A pointer to any attribute flags associated with the parameter.</span></span> <span data-ttu-id="c2c95-113">Это битовая маска `CorParamAttr` значения.</span><span class="sxs-lookup"><span data-stu-id="c2c95-113">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="c2c95-114">[out] Указатель на значение типа, указывающее флаг, параметр <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="c2c95-114">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="c2c95-115">[out] Указатель на строковую константу, возвращаемых параметром.</span><span class="sxs-lookup"><span data-stu-id="c2c95-115">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="c2c95-116">[out] Размер `ppValue` в расширенные символы, или нуль, если `ppValue` не содержит строку.</span><span class="sxs-lookup"><span data-stu-id="c2c95-116">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2c95-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2c95-117">Remarks</span></span>

<span data-ttu-id="c2c95-118">Последовательность значений элементов в `pulSequence` начинаются с 1 для параметров.</span><span class="sxs-lookup"><span data-stu-id="c2c95-118">The sequence values in `pulSequence` begin with 1 for parameters.</span></span> <span data-ttu-id="c2c95-119">Возвращаемое значение имеет порядковый номер 0.</span><span class="sxs-lookup"><span data-stu-id="c2c95-119">A return value has a sequence number of 0.</span></span>

## <a name="requirements"></a><span data-ttu-id="c2c95-120">Требования</span><span class="sxs-lookup"><span data-stu-id="c2c95-120">Requirements</span></span>  
 <span data-ttu-id="c2c95-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2c95-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2c95-122">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c2c95-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2c95-123">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c2c95-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2c95-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2c95-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2c95-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c2c95-125">See also</span></span>

- [<span data-ttu-id="c2c95-126">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c2c95-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c2c95-127">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c2c95-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
