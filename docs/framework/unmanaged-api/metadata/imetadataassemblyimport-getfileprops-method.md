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
ms.openlocfilehash: beb697d80417b937876a0887e4376341185a47d9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447212"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="62231-102">Метод IMetaDataAssemblyImport::GetFileProps</span><span class="sxs-lookup"><span data-stu-id="62231-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="62231-103">Возвращает свойства файла с указанной сигнатурой метаданных.</span><span class="sxs-lookup"><span data-stu-id="62231-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62231-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62231-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="62231-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="62231-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="62231-106">окне `mdFile` маркер метаданных, представляющий файл, для которого необходимо получить свойства.</span><span class="sxs-lookup"><span data-stu-id="62231-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="62231-107">заполняет Простое имя файла.</span><span class="sxs-lookup"><span data-stu-id="62231-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="62231-108">окне Размер `szName`в расширенных символах.</span><span class="sxs-lookup"><span data-stu-id="62231-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="62231-109">заполняет Число расширенных символов, фактически возвращаемых в `szName`.</span><span class="sxs-lookup"><span data-stu-id="62231-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="62231-110">заполняет Указатель на хэш-значение.</span><span class="sxs-lookup"><span data-stu-id="62231-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="62231-111">Это хэш-код с использованием алгоритма SHA-1 файла.</span><span class="sxs-lookup"><span data-stu-id="62231-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="62231-112">заполняет Число расширенных символов в возвращенном хэш-значении.</span><span class="sxs-lookup"><span data-stu-id="62231-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="62231-113">заполняет Указатель на флаги, описывающие метаданные, примененные к файлу.</span><span class="sxs-lookup"><span data-stu-id="62231-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="62231-114">Значение Flags является сочетанием одного или нескольких значений [корфилефлагс](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="62231-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62231-115">Требования</span><span class="sxs-lookup"><span data-stu-id="62231-115">Requirements</span></span>  
 <span data-ttu-id="62231-116">**Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62231-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62231-117">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="62231-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62231-118">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="62231-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="62231-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62231-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62231-120">См. также</span><span class="sxs-lookup"><span data-stu-id="62231-120">See also</span></span>

- [<span data-ttu-id="62231-121">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="62231-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
