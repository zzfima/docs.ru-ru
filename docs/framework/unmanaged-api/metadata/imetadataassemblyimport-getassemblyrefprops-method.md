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
ms.openlocfilehash: 4149db74adfa26df221eed5c590766a023bb105e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448225"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="b2fb8-102">Метод IMetaDataAssemblyImport::GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="b2fb8-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="b2fb8-103">Возвращает набор свойств для ссылки на сборку с указанной сигнатурой метаданных.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2fb8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2fb8-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b2fb8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2fb8-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="b2fb8-106">окне `mdAssemblyRef` маркер метаданных, представляющий ссылку на сборку, для которой необходимо получить свойства.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="b2fb8-107">заполняет Указатель на открытый ключ или маркер метаданных.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="b2fb8-108">заполняет Число байтов в возвращенном открытом ключе или токене.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="b2fb8-109">заполняет Простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="b2fb8-110">окне Размер `szName`в расширенных символах.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="b2fb8-111">заполняет Указатель на число расширенных символов, фактически возвращаемых в `szName`.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="b2fb8-112">заполняет Указатель на структуру ASSEMBLYMETADATA, содержащую метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="b2fb8-113">заполняет Указатель на хэш-значение.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="b2fb8-114">Это хэш с использованием алгоритма SHA-1 `PublicKey` свойства сборки, на которую указывает ссылка, если не задан флаг Арффуллоригинатор перечисления [ассемблиреффлагс](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="b2fb8-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="b2fb8-115">заполняет Число расширенных символов в возвращенном хэш-значении.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="b2fb8-116">заполняет Указатель на флаги, описывающие метаданные, примененные к сборке.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="b2fb8-117">Значение Flags является сочетанием одного или нескольких значений [корассемблифлагс](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="b2fb8-117">The flags value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2fb8-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b2fb8-118">Return Value</span></span>  
 <span data-ttu-id="b2fb8-119">Этот метод возвращает S_OK, если он выполнен. в противном случае возвращается один из кодов ошибок, определенных в файле заголовка Winerror. h.</span><span class="sxs-lookup"><span data-stu-id="b2fb8-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2fb8-120">Требования</span><span class="sxs-lookup"><span data-stu-id="b2fb8-120">Requirements</span></span>  
 <span data-ttu-id="b2fb8-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2fb8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2fb8-122">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="b2fb8-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b2fb8-123">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b2fb8-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b2fb8-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2fb8-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2fb8-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="b2fb8-125">See also</span></span>

- [<span data-ttu-id="b2fb8-126">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="b2fb8-126">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
