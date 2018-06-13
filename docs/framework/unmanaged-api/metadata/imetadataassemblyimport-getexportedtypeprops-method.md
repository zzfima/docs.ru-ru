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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c76e46c75680d9fc0ad70e94da288f0c6b5e5ee1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446324"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="ca098-102">Метод IMetaDataAssemblyImport::GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="ca098-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="ca098-103">Возвращает набор свойств экспортируемого типа с заданной подписью метаданных.</span><span class="sxs-lookup"><span data-stu-id="ca098-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca098-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca098-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="ca098-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca098-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="ca098-106">[in] `mdExportedType` Токен метаданных, представляющий экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="ca098-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="ca098-107">[out] Имя экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="ca098-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ca098-108">[in] Размер в расширенные символы из `szName`.</span><span class="sxs-lookup"><span data-stu-id="ca098-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ca098-109">[out] Число расширенных символов, фактически извлеченных в `szName`</span><span class="sxs-lookup"><span data-stu-id="ca098-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="ca098-110">[out] `mdFile`, `mdAssemblyRef`, Или `mdExportedType` токен метаданных, который содержит или разрешает доступ к свойствам экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="ca098-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="ca098-111">[out] Указатель на `mdTypeDef` токен, представляющий тип в файле.</span><span class="sxs-lookup"><span data-stu-id="ca098-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="ca098-112">[out] Указатель флаги, описывающие метаданные, применяемые к экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="ca098-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="ca098-113">Значение флагов может быть один или несколько [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) значения.</span><span class="sxs-lookup"><span data-stu-id="ca098-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca098-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ca098-114">Requirements</span></span>  
 <span data-ttu-id="ca098-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca098-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca098-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ca098-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ca098-117">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ca098-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ca098-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca098-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca098-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ca098-119">See Also</span></span>  
 [<span data-ttu-id="ca098-120">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="ca098-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
