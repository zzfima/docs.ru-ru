---
title: Метод IMetaDataAssemblyImport::GetExportedTypeProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
ms.openlocfilehash: 15b58e01d4ce99f19f510c760819471b84380b45
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177758"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="bd9dc-102">Метод IMetaDataAssemblyImport::GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="bd9dc-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="bd9dc-103">Получает набор свойств экспортируемого типа с указанной подписью метаданных.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd9dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd9dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,
    [out] LPWSTR            szName,
    [in]  ULONG             cchName,
    [out] ULONG             *pchName,
    [out] mdToken           *ptkImplementation,
    [out] mdTypeDef         *ptkTypeDef,
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd9dc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bd9dc-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="bd9dc-106">(в) Токен `mdExportedType` метаданных, представляющий экспортированный тип.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="bd9dc-107">(ваут) Название экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="bd9dc-108">(в) Размер, в широких символов, из `szName`.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="bd9dc-109">(ваут) Количество широких символов фактически вернулся в`szName`</span><span class="sxs-lookup"><span data-stu-id="bd9dc-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="bd9dc-110">(ваут) `mdFile`Токен `mdAssemblyRef`метаданных, содержащий или позволяющий получить доступ к свойствам экспортируемого типа, или `mdExportedType` метаданный.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="bd9dc-111">(ваут) Указатель на `mdTypeDef` маркер, представляющий тип файла.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="bd9dc-112">(ваут) Указатель на флаги, описывающие метаданные, применяемые к экспортируемому типу.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="bd9dc-113">Значение флагов может быть одним или более значениями [CorTypeAttr.](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="bd9dc-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd9dc-114">Требования</span><span class="sxs-lookup"><span data-stu-id="bd9dc-114">Requirements</span></span>  
 <span data-ttu-id="bd9dc-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd9dc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd9dc-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bd9dc-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd9dc-117">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bd9dc-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd9dc-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd9dc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd9dc-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bd9dc-119">See also</span></span>

- [<span data-ttu-id="bd9dc-120">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="bd9dc-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
