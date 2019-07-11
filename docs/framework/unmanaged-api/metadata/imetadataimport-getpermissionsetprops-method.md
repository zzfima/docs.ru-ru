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
ms.openlocfilehash: 48cd62f89f1112a1007a5661dc55fe2977dace2b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778920"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="d9865-102">Метод IMetaDataImport::GetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="d9865-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="d9865-103">Возвращает метаданные, связанные с <xref:System.Security.PermissionSet?displayProperty=nameWithType> представленного указанным токеном Permission.</span><span class="sxs-lookup"><span data-stu-id="d9865-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9865-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9865-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9865-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9865-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="d9865-106">[in] Токен метаданных разрешение, представляющее набор разрешений, чтобы получить метаданные свойства.</span><span class="sxs-lookup"><span data-stu-id="d9865-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="d9865-107">[out] Указатель на набор разрешений.</span><span class="sxs-lookup"><span data-stu-id="d9865-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="d9865-108">[out] Указатель на двоичную подпись метаданных набора разрешений.</span><span class="sxs-lookup"><span data-stu-id="d9865-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="d9865-109">[out] Размер в байтах `ppvPermission`.</span><span class="sxs-lookup"><span data-stu-id="d9865-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9865-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d9865-110">Requirements</span></span>  
 <span data-ttu-id="d9865-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9865-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9865-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d9865-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9865-113">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d9865-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9865-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9865-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9865-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d9865-115">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="d9865-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d9865-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d9865-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d9865-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
