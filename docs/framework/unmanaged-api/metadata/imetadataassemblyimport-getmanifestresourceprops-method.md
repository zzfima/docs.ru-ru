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
ms.openlocfilehash: c1792ed0f15f8cfb62567593c9694453650f0bb9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436315"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="be437-102">Метод IMetaDataAssemblyImport::GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="be437-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="be437-103">Возвращает набор свойств ресурса манифеста с указанной сигнатурой метаданных.</span><span class="sxs-lookup"><span data-stu-id="be437-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be437-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be437-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="be437-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="be437-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="be437-106">окне Токен `mdManifestResource`, представляющий ресурс, для которого необходимо получить свойства.</span><span class="sxs-lookup"><span data-stu-id="be437-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="be437-107">заполняет Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="be437-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="be437-108">окне Размер `szName`в расширенных символах.</span><span class="sxs-lookup"><span data-stu-id="be437-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="be437-109">заполняет Указатель на число расширенных символов, фактически возвращаемых в `szName`.</span><span class="sxs-lookup"><span data-stu-id="be437-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="be437-110">заполняет Указатель на маркер `mdFile` или маркер `mdAssemblyRef`, представляющий файл или сборку соответственно, который содержит ресурс.</span><span class="sxs-lookup"><span data-stu-id="be437-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="be437-111">заполняет Указатель на значение, указывающее смещение к началу ресурса в файле.</span><span class="sxs-lookup"><span data-stu-id="be437-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="be437-112">заполняет Указатель на флаги, описывающие метаданные, применяемые к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="be437-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="be437-113">Значение Flags является сочетанием одного или нескольких значений [корманифестресаурцефлагс](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="be437-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be437-114">Требования</span><span class="sxs-lookup"><span data-stu-id="be437-114">Requirements</span></span>  
 <span data-ttu-id="be437-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be437-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be437-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="be437-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="be437-117">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="be437-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="be437-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be437-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be437-119">См. также</span><span class="sxs-lookup"><span data-stu-id="be437-119">See also</span></span>

- [<span data-ttu-id="be437-120">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="be437-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
