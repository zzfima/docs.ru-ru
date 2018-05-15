---
title: Метод IMetaDataImport::GetPermissionSetProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be9b2fa3037dc00bce52d9ff89291d1c02cffc38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="fa857-102">Метод IMetaDataImport::GetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="fa857-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="fa857-103">Возвращает метаданные, связанные с <xref:System.Security.PermissionSet?displayProperty=nameWithType> представленного указанным токеном Permission.</span><span class="sxs-lookup"><span data-stu-id="fa857-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa857-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa857-104">Syntax</span></span>  
  
```  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa857-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fa857-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="fa857-106">[in] Токен метаданных разрешений, представляющий набор разрешений для получения метаданных свойства.</span><span class="sxs-lookup"><span data-stu-id="fa857-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="fa857-107">[out] Указатель на набор разрешений.</span><span class="sxs-lookup"><span data-stu-id="fa857-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="fa857-108">[out] Указатель на двоичную подпись метаданных набора разрешений.</span><span class="sxs-lookup"><span data-stu-id="fa857-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="fa857-109">[out] Размер в байтах `ppvPermission`.</span><span class="sxs-lookup"><span data-stu-id="fa857-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa857-110">Требования</span><span class="sxs-lookup"><span data-stu-id="fa857-110">Requirements</span></span>  
 <span data-ttu-id="fa857-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa857-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa857-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fa857-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa857-113">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa857-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fa857-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa857-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa857-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fa857-115">See Also</span></span>  
 <xref:System.Security.PermissionSet>  
 [<span data-ttu-id="fa857-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="fa857-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="fa857-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="fa857-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
