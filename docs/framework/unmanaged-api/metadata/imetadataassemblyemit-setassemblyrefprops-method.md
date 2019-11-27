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
ms.openlocfilehash: 5434aa2d12bd9a29a8c2fc784421442469ceb1ce
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440564"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="60b45-102">Метод IMetaDataAssemblyEmit::SetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="60b45-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="60b45-103">Изменяет указанную структуру метаданных `AssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="60b45-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60b45-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60b45-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="60b45-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="60b45-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="60b45-106">окне Маркер метаданных, указывающий структуру метаданных `AssemblyRef`, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="60b45-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="60b45-107">окне Открытый ключ издателя сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="60b45-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="60b45-108">окне Размер в байтах `pbPublicKeyOrToken`.</span><span class="sxs-lookup"><span data-stu-id="60b45-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="60b45-109">окне Понятное для человека текстовое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="60b45-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="60b45-110">окне Указатель на экземпляр ASSEMBLYMETADATA, содержащий сведения о версии, платформе и локали для сборки.</span><span class="sxs-lookup"><span data-stu-id="60b45-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="60b45-111">окне Указатель на хэш-данные, связанные со сборкой.</span><span class="sxs-lookup"><span data-stu-id="60b45-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="60b45-112">окне Размер в байтах `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="60b45-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="60b45-113">окне Побитовое сочетание значений [ассемблиреффлагс](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) , задающих атрибуты упоминаемой сборки.</span><span class="sxs-lookup"><span data-stu-id="60b45-113">[in] A bitwise combination of [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60b45-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="60b45-114">Remarks</span></span>  
 <span data-ttu-id="60b45-115">Чтобы создать `AssemblyRef` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефинеассемблиреф](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) .</span><span class="sxs-lookup"><span data-stu-id="60b45-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60b45-116">Требования</span><span class="sxs-lookup"><span data-stu-id="60b45-116">Requirements</span></span>  
 <span data-ttu-id="60b45-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60b45-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60b45-118">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="60b45-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="60b45-119">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="60b45-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="60b45-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60b45-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60b45-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="60b45-121">See also</span></span>

- [<span data-ttu-id="60b45-122">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="60b45-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
