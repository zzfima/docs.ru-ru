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
ms.openlocfilehash: e948644e4f2d91b2f1e3e3627f7adbe204dee9d4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155419"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="5d584-102">Метод IMetaDataImport::GetModuleRefProps</span><span class="sxs-lookup"><span data-stu-id="5d584-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="5d584-103">Возвращает имя модуля, на который ссылается указанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="5d584-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d584-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d584-104">Syntax</span></span>  
  
```  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,   
   [in]  ULONG               cchName,   
   [out] ULONG               *pchName   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d584-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d584-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="5d584-106">[in] Маркер метаданных ModuleRef, ссылающийся на модуль, чтобы получить сведения о метаданных.</span><span class="sxs-lookup"><span data-stu-id="5d584-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="5d584-107">[out] Буфер для хранения имени модуля.</span><span class="sxs-lookup"><span data-stu-id="5d584-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="5d584-108">[in] Запрошенный размер `szName` в расширенных символах.</span><span class="sxs-lookup"><span data-stu-id="5d584-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="5d584-109">[out] Возвращаемый размер `szName` в расширенных символах.</span><span class="sxs-lookup"><span data-stu-id="5d584-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d584-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5d584-110">Requirements</span></span>  
 <span data-ttu-id="5d584-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d584-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d584-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5d584-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d584-113">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d584-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5d584-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d584-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d584-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5d584-115">See also</span></span>

- [<span data-ttu-id="5d584-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5d584-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5d584-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5d584-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
