---
title: Метод IMetaDataEmit::SetPermissionSetProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 510c33b8e0e26bead00dcb85a6ceba102a5f267d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163778"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="dd402-102">Метод IMetaDataEmit::SetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="dd402-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="dd402-103">Задает или обновляет функции сигнатуры метаданных набора разрешений, определенные с помощью предыдущего вызова [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="dd402-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd402-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd402-104">Syntax</span></span>  
  
```  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd402-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dd402-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="dd402-106">[in] Токен метаданных, представляющий объект параметризация.</span><span class="sxs-lookup"><span data-stu-id="dd402-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="dd402-107">[in] Объект [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) значение, указывающее тип декларативной безопасности для использования.</span><span class="sxs-lookup"><span data-stu-id="dd402-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="dd402-108">[in] Разрешение BLOB-ОБЪЕКТОВ.</span><span class="sxs-lookup"><span data-stu-id="dd402-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="dd402-109">[in] Размер в байтах из `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="dd402-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="dd402-110">[out] `mdPermission` Токен метаданных, представляющий обновленные разрешения.</span><span class="sxs-lookup"><span data-stu-id="dd402-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd402-111">Требования</span><span class="sxs-lookup"><span data-stu-id="dd402-111">Requirements</span></span>  
 <span data-ttu-id="dd402-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd402-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd402-113">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dd402-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dd402-114">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd402-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd402-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd402-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd402-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dd402-116">See also</span></span>

- [<span data-ttu-id="dd402-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="dd402-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="dd402-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="dd402-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
