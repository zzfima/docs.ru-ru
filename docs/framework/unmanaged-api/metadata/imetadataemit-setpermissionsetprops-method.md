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
ms.openlocfilehash: 8d80e3206f74c3c50c8436563b0e39d1229a963b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="81aab-102">Метод IMetaDataEmit::SetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="81aab-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="81aab-103">Задает или обновляет подпись метаданных для набора разрешений, определенных во время предыдущего вызова для функции [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="81aab-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81aab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81aab-104">Syntax</span></span>  
  
```  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81aab-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="81aab-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="81aab-106">[in] Токен метаданных, представляющий объект параметризация.</span><span class="sxs-lookup"><span data-stu-id="81aab-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="81aab-107">[in] Объект [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) значение, указывающее тип декларативной безопасности для использования.</span><span class="sxs-lookup"><span data-stu-id="81aab-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="81aab-108">[in] Разрешение большого двоичного ОБЪЕКТА.</span><span class="sxs-lookup"><span data-stu-id="81aab-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="81aab-109">[in] Размер в байтах для `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="81aab-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="81aab-110">[out] `mdPermission` Токен метаданных, представляющий обновленные разрешения.</span><span class="sxs-lookup"><span data-stu-id="81aab-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81aab-111">Требования</span><span class="sxs-lookup"><span data-stu-id="81aab-111">Requirements</span></span>  
 <span data-ttu-id="81aab-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81aab-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81aab-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="81aab-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="81aab-114">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="81aab-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81aab-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81aab-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81aab-116">См. также</span><span class="sxs-lookup"><span data-stu-id="81aab-116">See Also</span></span>  
 [<span data-ttu-id="81aab-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="81aab-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="81aab-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="81aab-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
