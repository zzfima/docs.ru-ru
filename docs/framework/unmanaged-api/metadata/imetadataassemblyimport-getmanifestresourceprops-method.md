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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ba99d84686974b425bcdee0bbf4770e4843e1351
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992580"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="0d118-102">Метод IMetaDataAssemblyImport::GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="0d118-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="0d118-103">Получает набор свойств ресурса манифеста с заданной подписью метаданных.</span><span class="sxs-lookup"><span data-stu-id="0d118-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d118-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d118-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="0d118-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d118-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="0d118-106">[in] `mdManifestResource` Токен, представляющий ресурс, для которого нужно получить свойства.</span><span class="sxs-lookup"><span data-stu-id="0d118-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="0d118-107">[out] Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="0d118-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="0d118-108">[in] Размер, в расширенных символах из `szName`.</span><span class="sxs-lookup"><span data-stu-id="0d118-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="0d118-109">[out] Указатель на число расширенных символов, фактически возвращенных в `szName`.</span><span class="sxs-lookup"><span data-stu-id="0d118-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="0d118-110">[out] Указатель на `mdFile` маркеров или `mdAssemblyRef` токен, который представляет файл или сборку, соответственно, содержащего ресурс.</span><span class="sxs-lookup"><span data-stu-id="0d118-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="0d118-111">[out] Указатель на значение, указывающее смещение в начало ресурса в файле.</span><span class="sxs-lookup"><span data-stu-id="0d118-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="0d118-112">[out] Указатель на флаги, описывающие метаданные, применяемые к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="0d118-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="0d118-113">Значение флагов представляет собой сочетание одного или нескольких [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) значения.</span><span class="sxs-lookup"><span data-stu-id="0d118-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d118-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0d118-114">Requirements</span></span>  
 <span data-ttu-id="0d118-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d118-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d118-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0d118-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d118-117">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d118-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0d118-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d118-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d118-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0d118-119">See also</span></span>

- [<span data-ttu-id="0d118-120">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="0d118-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
