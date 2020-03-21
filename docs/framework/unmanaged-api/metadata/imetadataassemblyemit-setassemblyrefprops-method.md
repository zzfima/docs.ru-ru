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
ms.openlocfilehash: 6ad6bbb8a4c69f575bbeba3a297c46e049a97325
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176049"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="0f6de-102">Метод IMetaDataAssemblyEmit::SetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="0f6de-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="0f6de-103">Изменяет указанную структуру метаданных `AssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="0f6de-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f6de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f6de-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="0f6de-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0f6de-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="0f6de-106">(в) Токен метаданных, который определяет `AssemblyRef` структуру метаданных для изменения.</span><span class="sxs-lookup"><span data-stu-id="0f6de-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="0f6de-107">(в) Открытый ключ издателя ссылки сборки.</span><span class="sxs-lookup"><span data-stu-id="0f6de-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="0f6de-108">(в) Размер байтов `pbPublicKeyOrToken`.</span><span class="sxs-lookup"><span data-stu-id="0f6de-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="0f6de-109">(в) Читаемое человеком текстовое название сборки.</span><span class="sxs-lookup"><span data-stu-id="0f6de-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="0f6de-110">(в) Указатель на экземпляр ASSEMBLYMETADATA, содержащий информацию о версии, платформе и локализации для сборки.</span><span class="sxs-lookup"><span data-stu-id="0f6de-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="0f6de-111">(в) Указатель на хэш-данные, связанные с сборкой.</span><span class="sxs-lookup"><span data-stu-id="0f6de-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="0f6de-112">(в) Размер байтов `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="0f6de-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="0f6de-113">(в) Битовая комбинация значений [AssemblyRefFlags,](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) которые указывают атрибуты указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="0f6de-113">[in] A bitwise combination of [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f6de-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f6de-114">Remarks</span></span>  
 <span data-ttu-id="0f6de-115">Для создания `AssemblyRef` структуры метаданных используйте метод [IMetaDataAssemblyEmit::DefineAssemblyRef.](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)</span><span class="sxs-lookup"><span data-stu-id="0f6de-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f6de-116">Требования</span><span class="sxs-lookup"><span data-stu-id="0f6de-116">Requirements</span></span>  
 <span data-ttu-id="0f6de-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f6de-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f6de-118">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0f6de-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f6de-119">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0f6de-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0f6de-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f6de-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f6de-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0f6de-121">See also</span></span>

- [<span data-ttu-id="0f6de-122">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="0f6de-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
