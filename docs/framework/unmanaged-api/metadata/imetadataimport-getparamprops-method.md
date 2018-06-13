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
ms.openlocfilehash: 95850448504fd863f2726a7fb7574436476a6dc5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449329"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="9ee44-102">Метод IMetaDataImport::GetParamProps</span><span class="sxs-lookup"><span data-stu-id="9ee44-102">IMetaDataImport::GetParamProps Method</span></span>
<span data-ttu-id="9ee44-103">Возвращает значения метаданных для параметра, на который ссылается указанный токен ParamDef.</span><span class="sxs-lookup"><span data-stu-id="9ee44-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ee44-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ee44-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="9ee44-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ee44-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="9ee44-106">[in] Токен ParamDef, который представляет метаданные для возвращаемого параметра.</span><span class="sxs-lookup"><span data-stu-id="9ee44-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="9ee44-107">[out] Указатель на токен MethodDef, предоставляющий метод, который принимает параметр.</span><span class="sxs-lookup"><span data-stu-id="9ee44-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="9ee44-108">[out] Порядковый номер параметра в списке аргументов метода.</span><span class="sxs-lookup"><span data-stu-id="9ee44-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="9ee44-109">[out] Буфер для хранения имени параметра.</span><span class="sxs-lookup"><span data-stu-id="9ee44-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="9ee44-110">[in] Запрошенный размер в расширенных символах с `szName`.</span><span class="sxs-lookup"><span data-stu-id="9ee44-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="9ee44-111">[out] Возвращаемый размер в расширенных символах с `szName`.</span><span class="sxs-lookup"><span data-stu-id="9ee44-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="9ee44-112">[out] Указатель на любой атрибут флаги, связанные с параметром.</span><span class="sxs-lookup"><span data-stu-id="9ee44-112">[out] A pointer to any attribute flags associated with the parameter.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="9ee44-113">[out] Указатель на флаг, определяют, параметр <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="9ee44-113">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="9ee44-114">[out] Указатель на строковую константу, возвращаемых параметром.</span><span class="sxs-lookup"><span data-stu-id="9ee44-114">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="9ee44-115">[out] Размер `ppValue` в расширенные символы, или нуль, если `ppValue` не содержит строку.</span><span class="sxs-lookup"><span data-stu-id="9ee44-115">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ee44-116">Требования</span><span class="sxs-lookup"><span data-stu-id="9ee44-116">Requirements</span></span>  
 <span data-ttu-id="9ee44-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ee44-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ee44-118">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9ee44-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9ee44-119">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9ee44-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9ee44-120">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ee44-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ee44-121">См. также</span><span class="sxs-lookup"><span data-stu-id="9ee44-121">See Also</span></span>  
 [<span data-ttu-id="9ee44-122">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="9ee44-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="9ee44-123">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="9ee44-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
