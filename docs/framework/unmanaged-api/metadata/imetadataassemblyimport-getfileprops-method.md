---
title: "Метод IMetaDataAssemblyImport::GetFileProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetFileProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 55984c4adaf291e3b962514cdc3bea964d1c91bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="5cc30-102">Метод IMetaDataAssemblyImport::GetFileProps</span><span class="sxs-lookup"><span data-stu-id="5cc30-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="5cc30-103">Получает свойства файла с заданной подписью метаданных.</span><span class="sxs-lookup"><span data-stu-id="5cc30-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cc30-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cc30-104">Syntax</span></span>  
  
```  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,   
    [out] LPWSTR      szName,   
    [in]  ULONG       cchName,   
    [out] ULONG       *pchName,   
    [out] const void  **ppbHashValue,   
    [out] ULONG       *pcbHashValue,   
    [out] DWORD       *pdwFileFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5cc30-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5cc30-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="5cc30-106">[in] `mdFile` Токен метаданных, который представляет файл, для которого нужно получить свойства.</span><span class="sxs-lookup"><span data-stu-id="5cc30-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="5cc30-107">[out] Простое имя файла.</span><span class="sxs-lookup"><span data-stu-id="5cc30-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="5cc30-108">[in] Размер в расширенных символов из `szName`.</span><span class="sxs-lookup"><span data-stu-id="5cc30-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="5cc30-109">[out] Число расширенных символов, фактически извлеченных в `szName`.</span><span class="sxs-lookup"><span data-stu-id="5cc30-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="5cc30-110">[out] Указатель с хэш-значением.</span><span class="sxs-lookup"><span data-stu-id="5cc30-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="5cc30-111">Это хэш, с помощью алгоритма SHA-1, файла.</span><span class="sxs-lookup"><span data-stu-id="5cc30-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="5cc30-112">[out] Число расширенных символов в возвращенное хэш-значение.</span><span class="sxs-lookup"><span data-stu-id="5cc30-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="5cc30-113">[out] Указатель флаги, описывающие метаданные, применяемые в файл.</span><span class="sxs-lookup"><span data-stu-id="5cc30-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="5cc30-114">Значение флагов представляет собой сочетание одного или нескольких [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) значения.</span><span class="sxs-lookup"><span data-stu-id="5cc30-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cc30-115">Требования</span><span class="sxs-lookup"><span data-stu-id="5cc30-115">Requirements</span></span>  
 <span data-ttu-id="5cc30-116">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cc30-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cc30-117">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5cc30-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5cc30-118">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5cc30-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5cc30-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cc30-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cc30-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5cc30-120">See Also</span></span>  
 [<span data-ttu-id="5cc30-121">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="5cc30-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
