---
title: Метод IMetaDataAssemblyImport::GetFileProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
ms.openlocfilehash: dae4a36537eeac58ffb17ebc1b78d935ec807cd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175984"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="86ea0-102">Метод IMetaDataAssemblyImport::GetFileProps</span><span class="sxs-lookup"><span data-stu-id="86ea0-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="86ea0-103">Получает свойства файла с указанной подписью метаданных.</span><span class="sxs-lookup"><span data-stu-id="86ea0-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86ea0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86ea0-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="86ea0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="86ea0-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="86ea0-106">(в) Токен `mdFile` метаданных, представляющий файл, для которого можно получить свойства.</span><span class="sxs-lookup"><span data-stu-id="86ea0-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="86ea0-107">(ваут) Простое название файла.</span><span class="sxs-lookup"><span data-stu-id="86ea0-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="86ea0-108">(в) Размер, в широких chars, . `szName`</span><span class="sxs-lookup"><span data-stu-id="86ea0-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="86ea0-109">(ваут) Количество широких chars фактически `szName`вернулся в .</span><span class="sxs-lookup"><span data-stu-id="86ea0-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="86ea0-110">(ваут) Указатель на значение хэша.</span><span class="sxs-lookup"><span data-stu-id="86ea0-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="86ea0-111">Это хэш, использующий алгоритм SHA-1, файла.</span><span class="sxs-lookup"><span data-stu-id="86ea0-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="86ea0-112">(ваут) Количество широких chars в возвращенном значении хэша.</span><span class="sxs-lookup"><span data-stu-id="86ea0-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="86ea0-113">(ваут) Указатель на флаги, описывающие метаданные, применяемые к файлу.</span><span class="sxs-lookup"><span data-stu-id="86ea0-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="86ea0-114">Значение флагов представляет собой сочетание одного или нескольких значений [CorFileFlags.](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="86ea0-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86ea0-115">Требования</span><span class="sxs-lookup"><span data-stu-id="86ea0-115">Requirements</span></span>  
 <span data-ttu-id="86ea0-116">**Платформа:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86ea0-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86ea0-117">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="86ea0-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="86ea0-118">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="86ea0-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="86ea0-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86ea0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86ea0-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="86ea0-120">See also</span></span>

- [<span data-ttu-id="86ea0-121">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="86ea0-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
