---
title: Метод IMetaDataAssemblyEmit::SetFileProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8017f816632cffc42676761a367e980d1cafe088
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443620"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="24d65-102">Метод IMetaDataAssemblyEmit::SetFileProps</span><span class="sxs-lookup"><span data-stu-id="24d65-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="24d65-103">Изменяет указанную структуру метаданных `File`.</span><span class="sxs-lookup"><span data-stu-id="24d65-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24d65-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24d65-104">Syntax</span></span>  
  
```  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24d65-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="24d65-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="24d65-106">[in] Токен метаданных, указывает `File` изменение структуры метаданных.</span><span class="sxs-lookup"><span data-stu-id="24d65-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="24d65-107">[in] Указатель на данные хэш, связанный с файлом.</span><span class="sxs-lookup"><span data-stu-id="24d65-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="24d65-108">[in] Размер в байтах `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="24d65-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="24d65-109">[in] Побитовое сочетание [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) значения, которые определяют различные атрибуты файла.</span><span class="sxs-lookup"><span data-stu-id="24d65-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24d65-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="24d65-110">Remarks</span></span>  
 <span data-ttu-id="24d65-111">Для создания `File` структуру метаданных, используйте [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="24d65-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24d65-112">Требования</span><span class="sxs-lookup"><span data-stu-id="24d65-112">Requirements</span></span>  
 <span data-ttu-id="24d65-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24d65-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24d65-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="24d65-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24d65-115">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="24d65-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="24d65-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24d65-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24d65-117">См. также</span><span class="sxs-lookup"><span data-stu-id="24d65-117">See Also</span></span>  
 [<span data-ttu-id="24d65-118">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="24d65-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
