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
ms.openlocfilehash: 25baa6ffda3d50915cc7898275d6a557c1b3e947
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176036"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="64ecf-102">Метод IMetaDataAssemblyEmit::SetFileProps</span><span class="sxs-lookup"><span data-stu-id="64ecf-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="64ecf-103">Изменяет указанную структуру метаданных `File`.</span><span class="sxs-lookup"><span data-stu-id="64ecf-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64ecf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64ecf-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64ecf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="64ecf-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="64ecf-106">(в) Токен метаданных, который определяет `File` структуру метаданных для изменения.</span><span class="sxs-lookup"><span data-stu-id="64ecf-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="64ecf-107">(в) Указатель на хэш-данные, связанные с файлом.</span><span class="sxs-lookup"><span data-stu-id="64ecf-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="64ecf-108">(в) Размер байтов `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="64ecf-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="64ecf-109">(в) Битовая комбинация значений [CorFileFlags,](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) определяющих различные атрибуты файла.</span><span class="sxs-lookup"><span data-stu-id="64ecf-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64ecf-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="64ecf-110">Remarks</span></span>  
 <span data-ttu-id="64ecf-111">Для создания `File` структуры метаданных используйте метод [IMetaDataAssemblyEmit::DefineFile.](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)</span><span class="sxs-lookup"><span data-stu-id="64ecf-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64ecf-112">Требования</span><span class="sxs-lookup"><span data-stu-id="64ecf-112">Requirements</span></span>  
 <span data-ttu-id="64ecf-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64ecf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64ecf-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="64ecf-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64ecf-115">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="64ecf-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="64ecf-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64ecf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ecf-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="64ecf-117">See also</span></span>

- [<span data-ttu-id="64ecf-118">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="64ecf-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
