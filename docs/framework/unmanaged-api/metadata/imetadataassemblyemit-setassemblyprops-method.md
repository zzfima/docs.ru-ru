---
title: Метод IMetaDataAssemblyEmit::SetAssemblyProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3361212f9a7f7ff0739e8544419a2b67abc8f457
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214654"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="27418-102">Метод IMetaDataAssemblyEmit::SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="27418-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>
<span data-ttu-id="27418-103">Изменяет указанную структуру метаданных `Assembly`.</span><span class="sxs-lookup"><span data-stu-id="27418-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27418-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27418-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27418-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="27418-105">Parameters</span></span>  
 `pma`  
 <span data-ttu-id="27418-106">[in] Токен метаданных, указывающее `Assembly` изменение структуры метаданных.</span><span class="sxs-lookup"><span data-stu-id="27418-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="27418-107">[in] Указатель на открытый ключ издателя сборки.</span><span class="sxs-lookup"><span data-stu-id="27418-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="27418-108">[in] Размер в байтах `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="27418-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="27418-109">[in] Идентификатор хэш-алгоритм, используемый для хэширования файлов сборки.</span><span class="sxs-lookup"><span data-stu-id="27418-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="27418-110">[in] Понятное текстовое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="27418-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="27418-111">[in] Указатель на ASSEMBLYMETADATA, содержащий сведения о версии, платформы и языка для сборки.</span><span class="sxs-lookup"><span data-stu-id="27418-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="27418-112">[in] Побитовое сочетание [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) значения, которые определяют различные атрибуты сборки.</span><span class="sxs-lookup"><span data-stu-id="27418-112">[in] A bitwise combination of [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27418-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="27418-113">Remarks</span></span>  
 <span data-ttu-id="27418-114">Чтобы создать `Assembly` структура метаданных, используйте [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="27418-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27418-115">Требования</span><span class="sxs-lookup"><span data-stu-id="27418-115">Requirements</span></span>  
 <span data-ttu-id="27418-116">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27418-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27418-117">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="27418-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27418-118">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27418-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="27418-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="27418-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="27418-120">См. также</span><span class="sxs-lookup"><span data-stu-id="27418-120">See also</span></span>

- [<span data-ttu-id="27418-121">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="27418-121">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
