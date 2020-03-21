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
ms.openlocfilehash: 9aef471c1155070af0e9bcca14975a65bc5dc763
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175971"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="96db3-102">Метод IMetaDataAssemblyImport::GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="96db3-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="96db3-103">Получает набор свойств для ссылки сборки с указанной подписью метаданных.</span><span class="sxs-lookup"><span data-stu-id="96db3-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96db3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96db3-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="96db3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="96db3-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="96db3-106">(в) Токен `mdAssemblyRef` метаданных, представляющий ссылку сборки для получения свойств.</span><span class="sxs-lookup"><span data-stu-id="96db3-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="96db3-107">(ваут) Указатель на открытый ключ или токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="96db3-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="96db3-108">(ваут) Количество байтов в возвращенном публичном ключе или маркере.</span><span class="sxs-lookup"><span data-stu-id="96db3-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="96db3-109">(ваут) Простое название сборки.</span><span class="sxs-lookup"><span data-stu-id="96db3-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="96db3-110">(в) Размер, в широких chars, . `szName`</span><span class="sxs-lookup"><span data-stu-id="96db3-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="96db3-111">(ваут) Указатель на количество широких chars `szName`фактически вернулся в .</span><span class="sxs-lookup"><span data-stu-id="96db3-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="96db3-112">(ваут) Указатель на структуру ASSEMBLYMETADATA, содержащую метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="96db3-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="96db3-113">(ваут) Указатель на значение хэша.</span><span class="sxs-lookup"><span data-stu-id="96db3-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="96db3-114">Это хэш, использующий алгоритм SHA-1, `PublicKey` имущества сборки, на который ссылается, если только не установлен флаг ArfFullOriginator в перечислении [AssemblyRefFlags.](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="96db3-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="96db3-115">(ваут) Количество широких chars в возвращенном значении хэша.</span><span class="sxs-lookup"><span data-stu-id="96db3-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="96db3-116">(ваут) Указатель на флаги, описывающие метаданные, применяемые к сборке.</span><span class="sxs-lookup"><span data-stu-id="96db3-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="96db3-117">Значение флагов представляет собой сочетание одного или нескольких значений [CorAssemblyFlags.](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="96db3-117">The flags value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96db3-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="96db3-118">Return Value</span></span>  
 <span data-ttu-id="96db3-119">Этот метод возвращает S_OK, если он преуспевает; в противном случае он возвращает один из кодов ошибок, определенных в файле заголовка Winerror.h.</span><span class="sxs-lookup"><span data-stu-id="96db3-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96db3-120">Требования</span><span class="sxs-lookup"><span data-stu-id="96db3-120">Requirements</span></span>  
 <span data-ttu-id="96db3-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96db3-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96db3-122">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="96db3-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="96db3-123">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="96db3-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="96db3-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96db3-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96db3-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="96db3-125">See also</span></span>

- [<span data-ttu-id="96db3-126">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="96db3-126">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
