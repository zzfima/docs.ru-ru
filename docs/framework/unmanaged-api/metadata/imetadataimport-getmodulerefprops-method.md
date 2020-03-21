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
ms.openlocfilehash: f46033b9e643ef6b4a0063c4995b8c024b8c1f7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175360"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="2624b-102">Метод IMetaDataImport::GetModuleRefProps</span><span class="sxs-lookup"><span data-stu-id="2624b-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="2624b-103">Возвращает имя модуля, на который ссылается указанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="2624b-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2624b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2624b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,
   [in]  ULONG               cchName,
   [out] ULONG               *pchName
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2624b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2624b-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="2624b-106">(в) Токен метаданных ModuleRef, который ссылается на модуль для получения информации о метаданных.</span><span class="sxs-lookup"><span data-stu-id="2624b-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="2624b-107">(ваут) Буфер для удержания имени модуля.</span><span class="sxs-lookup"><span data-stu-id="2624b-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="2624b-108">(в) Запрошенный размер `szName` в широких символах.</span><span class="sxs-lookup"><span data-stu-id="2624b-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="2624b-109">(ваут) Возвращаемый размер в широких `szName` символах.</span><span class="sxs-lookup"><span data-stu-id="2624b-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2624b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2624b-110">Requirements</span></span>  
 <span data-ttu-id="2624b-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2624b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2624b-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2624b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2624b-113">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2624b-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2624b-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2624b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2624b-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2624b-115">See also</span></span>

- [<span data-ttu-id="2624b-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="2624b-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2624b-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="2624b-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
