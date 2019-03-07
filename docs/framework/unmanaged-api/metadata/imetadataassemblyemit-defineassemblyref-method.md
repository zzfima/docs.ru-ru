---
title: Метод IMetaDataAssemblyEmit::DefineAssemblyRef
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 945972269871c3e78c19cc1038dd96a7f098b997
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57464585"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="ba144-102">Метод IMetaDataAssemblyEmit::DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="ba144-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>
<span data-ttu-id="ba144-103">Создает структуру `AssemblyRef`, содержащую метаданные для сборки, на которую ссылается данная сборка, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="ba144-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba144-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba144-104">Syntax</span></span>  
  
```  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba144-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba144-105">Parameters</span></span>  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="ba144-106">[in] Открытый ключ издателя по ссылке сборки.</span><span class="sxs-lookup"><span data-stu-id="ba144-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="ba144-107">Вспомогательная функция [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) может использоваться для получения хэша открытого ключа, передаваемое в качестве этого параметра.</span><span class="sxs-lookup"><span data-stu-id="ba144-107">The helper function [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="ba144-108">[in] Размер в байтах `pbPublicKeyOrToken`.</span><span class="sxs-lookup"><span data-stu-id="ba144-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="ba144-109">[in] Понятное текстовое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="ba144-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="ba144-110">Это значение не должна превышать 1024 символа.</span><span class="sxs-lookup"><span data-stu-id="ba144-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="ba144-111">[in] Экземпляр ASSEMBLYMETADATA, содержащий сведения о версии, платформы и языка сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="ba144-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="ba144-112">[in] Хэш данных, связанные со сборкой, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="ba144-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="ba144-113">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="ba144-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="ba144-114">[in] Размер в байтах `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="ba144-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="ba144-115">[in] Побитовое сочетание [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) значения, которые влияют на поведение подсистемы выполнения.</span><span class="sxs-lookup"><span data-stu-id="ba144-115">[in] A bitwise combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="ba144-116">[out] Указатель на возвращенный `AssemblyRef` токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="ba144-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba144-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="ba144-117">Remarks</span></span>  
 <span data-ttu-id="ba144-118">Один `AssemblyRef` структура метаданных должны быть определены для каждой сборки, на которую ссылается данная сборка.</span><span class="sxs-lookup"><span data-stu-id="ba144-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="ba144-119">Во время выполнения сведения о связанной сборке, передаются в котором распознаватель сборок с указанием, что они представляют сведения «при построении».</span><span class="sxs-lookup"><span data-stu-id="ba144-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="ba144-120">Затем, в котором распознаватель сборок применяет политику.</span><span class="sxs-lookup"><span data-stu-id="ba144-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba144-121">Требования</span><span class="sxs-lookup"><span data-stu-id="ba144-121">Requirements</span></span>  
 <span data-ttu-id="ba144-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba144-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba144-123">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ba144-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba144-124">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba144-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba144-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba144-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba144-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ba144-126">See also</span></span>
- [<span data-ttu-id="ba144-127">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="ba144-127">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
