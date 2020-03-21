---
title: Метод IMetaDataAssemblyImport::GetAssemblyProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
ms.openlocfilehash: dfa900e2184a8c415d75f5702c572b14c4018749
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177788"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="5d957-102">Метод IMetaDataAssemblyImport::GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="5d957-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="5d957-103">Получает набор свойств для сборки с указанной подписью метаданных.</span><span class="sxs-lookup"><span data-stu-id="5d957-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d957-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d957-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d957-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d957-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="5d957-106">[in].</span><span class="sxs-lookup"><span data-stu-id="5d957-106">[in].</span></span> <span data-ttu-id="5d957-107">Токен `mdAssembly` метаданных, представляющий сборку, для которой можно получить свойства.</span><span class="sxs-lookup"><span data-stu-id="5d957-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="5d957-108">(ваут) Указатель на открытый ключ или токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="5d957-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="5d957-109">(ваут) Количество байтов в возвращенном публичном ключе.</span><span class="sxs-lookup"><span data-stu-id="5d957-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="5d957-110">(ваут) Указатель на алгоритм, используемый для хэширования файлов в сборке.</span><span class="sxs-lookup"><span data-stu-id="5d957-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="5d957-111">(ваут) Простое название сборки.</span><span class="sxs-lookup"><span data-stu-id="5d957-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="5d957-112">(в) Размер, в широких chars, . `szName`</span><span class="sxs-lookup"><span data-stu-id="5d957-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="5d957-113">(ваут) Количество широких chars фактически `szName`вернулся в .</span><span class="sxs-lookup"><span data-stu-id="5d957-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="5d957-114">(ваут) Указатель на структуру ASSEMBLYMETADATA, содержащую метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="5d957-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="5d957-115">(ваут) Флаги, описывающие метаданные, применяемые к сборке.</span><span class="sxs-lookup"><span data-stu-id="5d957-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="5d957-116">Это значение представляет собой сочетание одного или нескольких значений [CorAssemblyFlags.](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="5d957-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d957-117">Требования</span><span class="sxs-lookup"><span data-stu-id="5d957-117">Requirements</span></span>  
 <span data-ttu-id="5d957-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d957-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d957-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5d957-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d957-120">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d957-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5d957-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d957-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d957-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5d957-122">See also</span></span>

- [<span data-ttu-id="5d957-123">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="5d957-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
