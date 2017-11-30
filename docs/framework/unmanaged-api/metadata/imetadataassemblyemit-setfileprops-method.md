---
title: "Метод IMetaDataAssemblyEmit::SetFileProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.SetFileProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f179ce3e54a5229423d7267cd52a97edef3b619d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="ea4fc-102">Метод IMetaDataAssemblyEmit::SetFileProps</span><span class="sxs-lookup"><span data-stu-id="ea4fc-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="ea4fc-103">Изменяет указанную структуру метаданных `File`.</span><span class="sxs-lookup"><span data-stu-id="ea4fc-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea4fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea4fc-104">Syntax</span></span>  
  
```  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea4fc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ea4fc-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="ea4fc-106">[in] Токен метаданных, указывает `File` изменение структуры метаданных.</span><span class="sxs-lookup"><span data-stu-id="ea4fc-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="ea4fc-107">[in] Указатель на данные хэш, связанный с файлом.</span><span class="sxs-lookup"><span data-stu-id="ea4fc-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="ea4fc-108">[in] Размер в байтах `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="ea4fc-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="ea4fc-109">[in] Побитовое сочетание [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) значения, которые определяют различные атрибуты файла.</span><span class="sxs-lookup"><span data-stu-id="ea4fc-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea4fc-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea4fc-110">Remarks</span></span>  
 <span data-ttu-id="ea4fc-111">Для создания `File` структуру метаданных, используйте [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="ea4fc-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea4fc-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ea4fc-112">Requirements</span></span>  
 <span data-ttu-id="ea4fc-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea4fc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea4fc-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ea4fc-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ea4fc-115">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea4fc-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ea4fc-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea4fc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea4fc-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ea4fc-117">See Also</span></span>  
 [<span data-ttu-id="ea4fc-118">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="ea4fc-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
