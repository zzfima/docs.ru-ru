---
title: Метод IMetaDataImport::GetModuleRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleRefProps
helpviewer_keywords:
- GetModuleRefProps method [.NET Framework metadata]
- IMetaDataImport::GetModuleRefProps method [.NET Framework metadata]
ms.assetid: b558e766-4c11-4628-ae47-b4e0a1800168
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 501c554f6e2e4ddd8abd21fe81b81d1898ea070b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583629"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="18c89-102">Метод IMetaDataImport::GetModuleRefProps</span><span class="sxs-lookup"><span data-stu-id="18c89-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="18c89-103">Возвращает имя модуля, на который ссылается указанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="18c89-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18c89-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18c89-104">Syntax</span></span>  
  
```  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,   
   [in]  ULONG               cchName,   
   [out] ULONG               *pchName   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18c89-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="18c89-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="18c89-106">[in] Маркер метаданных ModuleRef, ссылающийся на модуль, чтобы получить сведения о метаданных.</span><span class="sxs-lookup"><span data-stu-id="18c89-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="18c89-107">[out] Буфер для хранения имени модуля.</span><span class="sxs-lookup"><span data-stu-id="18c89-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="18c89-108">[in] Запрошенный размер `szName` в расширенных символах.</span><span class="sxs-lookup"><span data-stu-id="18c89-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="18c89-109">[out] Возвращаемый размер `szName` в расширенных символах.</span><span class="sxs-lookup"><span data-stu-id="18c89-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18c89-110">Требования</span><span class="sxs-lookup"><span data-stu-id="18c89-110">Requirements</span></span>  
 <span data-ttu-id="18c89-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18c89-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18c89-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="18c89-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="18c89-113">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="18c89-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="18c89-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18c89-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18c89-115">См. также</span><span class="sxs-lookup"><span data-stu-id="18c89-115">See also</span></span>
- [<span data-ttu-id="18c89-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="18c89-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="18c89-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="18c89-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
