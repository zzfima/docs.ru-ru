---
title: "Метод IMetaDataImport::GetModuleRefProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetModuleRefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetModuleRefProps
helpviewer_keywords:
- GetModuleRefProps method [.NET Framework metadata]
- IMetaDataImport::GetModuleRefProps method [.NET Framework metadata]
ms.assetid: b558e766-4c11-4628-ae47-b4e0a1800168
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 907743481cf036b7febf57d69ce428a250752c30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="f72c3-102">Метод IMetaDataImport::GetModuleRefProps</span><span class="sxs-lookup"><span data-stu-id="f72c3-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="f72c3-103">Возвращает имя модуля, на который ссылается указанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="f72c3-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f72c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f72c3-104">Syntax</span></span>  
  
```  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,   
   [in]  ULONG               cchName,   
   [out] ULONG               *pchName   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f72c3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f72c3-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="f72c3-106">[in] Токен метаданных ModuleRef, ссылающийся на модуль, чтобы получить сведения о метаданных.</span><span class="sxs-lookup"><span data-stu-id="f72c3-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="f72c3-107">[out] Буфер для хранения имени модуля.</span><span class="sxs-lookup"><span data-stu-id="f72c3-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="f72c3-108">[in] Запрошенный размер `szName` в расширенных символах.</span><span class="sxs-lookup"><span data-stu-id="f72c3-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="f72c3-109">[out] Возвращаемый размер `szName` в расширенных символах.</span><span class="sxs-lookup"><span data-stu-id="f72c3-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f72c3-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f72c3-110">Requirements</span></span>  
 <span data-ttu-id="f72c3-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f72c3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f72c3-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f72c3-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f72c3-113">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f72c3-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f72c3-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f72c3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72c3-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f72c3-115">See Also</span></span>  
 [<span data-ttu-id="f72c3-116">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="f72c3-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="f72c3-117">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="f72c3-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
