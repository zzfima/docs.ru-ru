---
title: "Метод IMetaDataEmit::DefinePermissionSet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefinePermissionSet
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 74bea316d3f56e007c4b75e6b801d8c82ae8ce96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="505f5-102">Метод IMetaDataEmit::DefinePermissionSet</span><span class="sxs-lookup"><span data-stu-id="505f5-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="505f5-103">Создает определение для набора разрешений с заданной подписью метаданных и получает маркер для этого определения набора разрешений.</span><span class="sxs-lookup"><span data-stu-id="505f5-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="505f5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="505f5-104">Syntax</span></span>  
  
```  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,   
    [in]  DWORD          dwAction,   
    [in]  void const     *pvPermission,   
    [in]  ULONG          cbPermission,   
    [out] mdPermission   *ppm   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="505f5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="505f5-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="505f5-106">[in] Объект параметризация.</span><span class="sxs-lookup"><span data-stu-id="505f5-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="505f5-107">[in] Объект [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) значение, указывающее тип декларативной безопасности для использования.</span><span class="sxs-lookup"><span data-stu-id="505f5-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="505f5-108">[in] Разрешение большого двоичного ОБЪЕКТА.</span><span class="sxs-lookup"><span data-stu-id="505f5-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="505f5-109">[in] Размер в байтах для `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="505f5-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="505f5-110">[out] Токен, возвращенный разрешение.</span><span class="sxs-lookup"><span data-stu-id="505f5-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="505f5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="505f5-111">Requirements</span></span>  
 <span data-ttu-id="505f5-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="505f5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="505f5-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="505f5-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="505f5-114">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="505f5-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="505f5-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="505f5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="505f5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="505f5-116">See Also</span></span>  
 [<span data-ttu-id="505f5-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="505f5-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="505f5-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="505f5-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
