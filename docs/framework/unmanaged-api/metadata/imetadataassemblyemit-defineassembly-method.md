---
title: Метод IMetaDataAssemblyEmit::DefineAssembly
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
ms.openlocfilehash: 14bd352099890e4ca36321d550b8e982d4373231
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177888"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="6e798-102">Метод IMetaDataAssemblyEmit::DefineAssembly</span><span class="sxs-lookup"><span data-stu-id="6e798-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="6e798-103">Создает `Assembly` структуру, содержащую метаданные для указанной сборки, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="6e798-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e798-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e798-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e798-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6e798-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="6e798-106">(в) Открытый ключ, который идентифицирует издателя сборки, или NULL, если сборка не названа решительно.</span><span class="sxs-lookup"><span data-stu-id="6e798-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="6e798-107">(в) Размер байтов `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="6e798-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="6e798-108">(в) Идентификатор алгоритма хэширования для шифрования файлов в сборке или NULL для указания алгоритма SHA-1.</span><span class="sxs-lookup"><span data-stu-id="6e798-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="6e798-109">(в) Читаемое человеком текстовое название сборки.</span><span class="sxs-lookup"><span data-stu-id="6e798-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="6e798-110">Это значение не должно превышать 1024 символов.</span><span class="sxs-lookup"><span data-stu-id="6e798-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="6e798-111">(в) Указатель на экземпляр ASSEMBLYMETADATA, содержащий информацию о версии, платформе и локализации для сборки.</span><span class="sxs-lookup"><span data-stu-id="6e798-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="6e798-112">(в) Сочетание значений [CorAssemblyFlags,](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) описывающие особенности сборки.</span><span class="sxs-lookup"><span data-stu-id="6e798-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="6e798-113">(ваут) Указатель на маркер метаданных.</span><span class="sxs-lookup"><span data-stu-id="6e798-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e798-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="6e798-114">Remarks</span></span>  
 <span data-ttu-id="6e798-115">Только `Assembly` одна структура метаданных может быть определена в манифесте.</span><span class="sxs-lookup"><span data-stu-id="6e798-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e798-116">Требования</span><span class="sxs-lookup"><span data-stu-id="6e798-116">Requirements</span></span>  
 <span data-ttu-id="6e798-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e798-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e798-118">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6e798-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e798-119">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6e798-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6e798-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e798-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e798-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6e798-121">See also</span></span>

- [<span data-ttu-id="6e798-122">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="6e798-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
