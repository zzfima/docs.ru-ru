---
title: Метод IMetaDataAssemblyImport::GetAssemblyRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e6c550ff7af2dda8bc06afd771024fe290339904
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089787"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="33afb-102">Метод IMetaDataAssemblyImport::GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="33afb-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="33afb-103">Получает набор свойств для ссылки на сборку с заданной подписью метаданных.</span><span class="sxs-lookup"><span data-stu-id="33afb-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33afb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33afb-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,   
    [out] const void          **ppbPublicKeyOrToken,   
    [out] ULONG                *pcbPublicKeyOrToken,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] ASSEMBLYMETADATA     *pMetaData,   
    [out] const void           **ppbHashValue,   
    [out] ULONG                *pcbHashValue,   
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33afb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="33afb-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="33afb-106">[in] `mdAssemblyRef` Маркер метаданных, представляющий ссылку на сборку, для которого нужно получить свойства.</span><span class="sxs-lookup"><span data-stu-id="33afb-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="33afb-107">[out] Указатель на открытый ключ или токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="33afb-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="33afb-108">[out] Число байтов в возвращаемый открытый ключ или маркер.</span><span class="sxs-lookup"><span data-stu-id="33afb-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="33afb-109">[out] Простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="33afb-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="33afb-110">[in] Размер, в расширенных символах из `szName`.</span><span class="sxs-lookup"><span data-stu-id="33afb-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="33afb-111">[out] Указатель на число расширенных символов, фактически возвращенных в `szName`.</span><span class="sxs-lookup"><span data-stu-id="33afb-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="33afb-112">[out] Указатель на структуру ASSEMBLYMETADATA, которая содержит метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="33afb-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="33afb-113">[out] Указатель на хэш-значения.</span><span class="sxs-lookup"><span data-stu-id="33afb-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="33afb-114">Это хэш, с помощью алгоритма SHA-1, из `PublicKey` свойство сборки, на которую выполняется ссылка, если флаг arfFullOriginator [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) имеет значение перечисления.</span><span class="sxs-lookup"><span data-stu-id="33afb-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="33afb-115">[out] Число расширенных символов в возвращенное хэш-значение.</span><span class="sxs-lookup"><span data-stu-id="33afb-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="33afb-116">[out] Указатель на флаги, описывающие метаданные, применяемые к сборке.</span><span class="sxs-lookup"><span data-stu-id="33afb-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="33afb-117">Значение флагов представляет собой сочетание одного или нескольких [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) значения.</span><span class="sxs-lookup"><span data-stu-id="33afb-117">The flags value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33afb-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="33afb-118">Return Value</span></span>  
 <span data-ttu-id="33afb-119">Этот метод возвращает значение S_OK, если он выполнен успешно; в противном случае возвращается один из кодов ошибок, определенных в файле заголовка Winerror.h.</span><span class="sxs-lookup"><span data-stu-id="33afb-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33afb-120">Требования</span><span class="sxs-lookup"><span data-stu-id="33afb-120">Requirements</span></span>  
 <span data-ttu-id="33afb-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33afb-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33afb-122">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="33afb-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="33afb-123">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33afb-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="33afb-124">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="33afb-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="33afb-125">См. также</span><span class="sxs-lookup"><span data-stu-id="33afb-125">See also</span></span>

- [<span data-ttu-id="33afb-126">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="33afb-126">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
