---
title: Метод IMetaDataAssemblyImport::GetManifestResourceProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
ms.openlocfilehash: d87d0d46ede65cf44c84edba92fe246174088a4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177661"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="8716a-102">Метод IMetaDataAssemblyImport::GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="8716a-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="8716a-103">Получает набор свойств ресурса манифеста с указанной подписью метаданных.</span><span class="sxs-lookup"><span data-stu-id="8716a-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8716a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8716a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] mdToken              *ptkImplementation,
    [out] DWORD                *pdwOffset,
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8716a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8716a-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="8716a-106">(в) Токен, `mdManifestResource` представляющий ресурс для получения свойств.</span><span class="sxs-lookup"><span data-stu-id="8716a-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="8716a-107">(ваут) Название ресурса.</span><span class="sxs-lookup"><span data-stu-id="8716a-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="8716a-108">(в) Размер, в широких chars, . `szName`</span><span class="sxs-lookup"><span data-stu-id="8716a-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="8716a-109">(ваут) Указатель на количество широких chars `szName`фактически вернулся в .</span><span class="sxs-lookup"><span data-stu-id="8716a-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="8716a-110">(ваут) Указатель на `mdFile` маркер или `mdAssemblyRef` маркер, представляющий файл или сборку, соответственно, содержащий ресурс.</span><span class="sxs-lookup"><span data-stu-id="8716a-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="8716a-111">(ваут) Указатель значения, опознававававававаемый смещением к началу ресурса в файле.</span><span class="sxs-lookup"><span data-stu-id="8716a-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="8716a-112">(ваут) Указатель на флаги, описывающие метаданные, применяемые к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="8716a-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="8716a-113">Значение флагов представляет собой сочетание одного или нескольких значений [CorManifestResourceFlags.](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="8716a-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8716a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8716a-114">Requirements</span></span>  
 <span data-ttu-id="8716a-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8716a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8716a-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8716a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8716a-117">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8716a-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8716a-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8716a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8716a-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8716a-119">See also</span></span>

- [<span data-ttu-id="8716a-120">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="8716a-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
