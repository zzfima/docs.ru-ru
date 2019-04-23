---
title: Метод IMetaDataAssemblyEmit::SetAssemblyRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 25d5e412dc52e4ce26995ff88454b33ccea64c89
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110101"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="0e1ed-102">Метод IMetaDataAssemblyEmit::SetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="0e1ed-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="0e1ed-103">Изменяет указанную структуру метаданных `AssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="0e1ed-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e1ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e1ed-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,   
    [in] const ASSEMBLYMETADATA     *pMetaData,   
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e1ed-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0e1ed-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="0e1ed-106">[in] Токен метаданных, указывающее `AssemblyRef` изменение структуры метаданных.</span><span class="sxs-lookup"><span data-stu-id="0e1ed-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="0e1ed-107">[in] Открытый ключ издателя по ссылке сборки.</span><span class="sxs-lookup"><span data-stu-id="0e1ed-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="0e1ed-108">[in] Размер в байтах `pbPublicKeyOrToken`.</span><span class="sxs-lookup"><span data-stu-id="0e1ed-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="0e1ed-109">[in] Понятное текстовое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="0e1ed-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="0e1ed-110">[in] Указатель на экземпляр ASSEMBLYMETADATA, содержащий сведения о версии, платформы и языковой стандарт для сборки.</span><span class="sxs-lookup"><span data-stu-id="0e1ed-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="0e1ed-111">[in] Указатель на данные хэша, связанные со сборкой.</span><span class="sxs-lookup"><span data-stu-id="0e1ed-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="0e1ed-112">[in] Размер в байтах `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="0e1ed-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="0e1ed-113">[in] Побитовое сочетание [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) значения, задающие атрибуты сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="0e1ed-113">[in] A bitwise combination of [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e1ed-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="0e1ed-114">Remarks</span></span>  
 <span data-ttu-id="0e1ed-115">Чтобы создать `AssemblyRef` структура метаданных, используйте [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="0e1ed-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e1ed-116">Требования</span><span class="sxs-lookup"><span data-stu-id="0e1ed-116">Requirements</span></span>  
 <span data-ttu-id="0e1ed-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e1ed-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e1ed-118">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0e1ed-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0e1ed-119">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0e1ed-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0e1ed-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e1ed-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e1ed-121">См. также</span><span class="sxs-lookup"><span data-stu-id="0e1ed-121">See also</span></span>

- [<span data-ttu-id="0e1ed-122">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="0e1ed-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
