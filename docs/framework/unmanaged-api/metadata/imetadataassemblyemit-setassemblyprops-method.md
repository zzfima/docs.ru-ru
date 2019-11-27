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
ms.openlocfilehash: f79320d5b7d2ad4ad44a79fae063ce6718490a70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431947"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="5111e-102">Метод IMetaDataAssemblyEmit::SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="5111e-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>
<span data-ttu-id="5111e-103">Изменяет указанную структуру метаданных `Assembly`.</span><span class="sxs-lookup"><span data-stu-id="5111e-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5111e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5111e-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="5111e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5111e-105">Parameters</span></span>  
 `pma`  
 <span data-ttu-id="5111e-106">окне Маркер метаданных, указывающий структуру метаданных `Assembly`, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="5111e-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="5111e-107">окне Указатель на открытый ключ издателя сборки.</span><span class="sxs-lookup"><span data-stu-id="5111e-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="5111e-108">окне Размер в байтах `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="5111e-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="5111e-109">окне Идентификатор хэш-алгоритма, используемого для хэширования файлов сборки.</span><span class="sxs-lookup"><span data-stu-id="5111e-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="5111e-110">окне Понятное для человека текстовое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="5111e-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="5111e-111">окне Указатель на ASSEMBLYMETADATA, содержащий сведения о версии, платформе и локали для сборки.</span><span class="sxs-lookup"><span data-stu-id="5111e-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="5111e-112">окне Побитовое сочетание значений [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) , задающих различные атрибуты сборки.</span><span class="sxs-lookup"><span data-stu-id="5111e-112">[in] A bitwise combination of [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5111e-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="5111e-113">Remarks</span></span>  
 <span data-ttu-id="5111e-114">Чтобы создать `Assembly` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефинеассембли](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5111e-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5111e-115">Требования</span><span class="sxs-lookup"><span data-stu-id="5111e-115">Requirements</span></span>  
 <span data-ttu-id="5111e-116">**Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5111e-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5111e-117">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="5111e-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5111e-118">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5111e-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5111e-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5111e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5111e-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="5111e-120">See also</span></span>

- [<span data-ttu-id="5111e-121">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="5111e-121">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
