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
ms.openlocfilehash: 5faf1a6ae89045b2ef17fab789ee6e5bf23eecf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175347"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="1b511-102">Метод IMetaDataImport::GetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="1b511-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="1b511-103">Получает метаданные, связанные <xref:System.Security.PermissionSet?displayProperty=nameWithType> с представленными указанным токеном «Разрешение».</span><span class="sxs-lookup"><span data-stu-id="1b511-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b511-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b511-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b511-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1b511-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="1b511-106">(в) Токен метаданных разрешения, представляющий набор разрешений для получения свойств метаданных.</span><span class="sxs-lookup"><span data-stu-id="1b511-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="1b511-107">(ваут) Указатель на набор разрешений.</span><span class="sxs-lookup"><span data-stu-id="1b511-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="1b511-108">(ваут) Указатель на двоичную подпись метаданных набора разрешений.</span><span class="sxs-lookup"><span data-stu-id="1b511-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="1b511-109">(ваут) Размер байтов `ppvPermission`.</span><span class="sxs-lookup"><span data-stu-id="1b511-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b511-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1b511-110">Requirements</span></span>  
 <span data-ttu-id="1b511-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b511-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b511-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1b511-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1b511-113">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1b511-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1b511-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b511-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b511-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1b511-115">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="1b511-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="1b511-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1b511-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="1b511-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
