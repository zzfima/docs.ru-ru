---
title: "Метод IMetaDataEmit::DefinePinvokeMap"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefinePinvokeMap
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0c15c6039f116597ee4f2c0f83bed4c5550b30a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="c23d7-102">Метод IMetaDataEmit::DefinePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="c23d7-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="c23d7-103">Задает функции сигнатуры PInvoke метода, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="c23d7-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c23d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c23d7-104">Syntax</span></span>  
  
```  
HRESULT DefinePinvokeMap (   
    [in]  mdToken            tk,   
    [in]  DWORD              dwMappingFlags,   
    [in]  LPCWSTR            szImportName,   
    [in]  mdModuleRef        mrImportDLL   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c23d7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c23d7-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="c23d7-106">[in] Токен для целевого метода.</span><span class="sxs-lookup"><span data-stu-id="c23d7-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="c23d7-107">[in] Флаги, используемые для сопоставления PInvoke.</span><span class="sxs-lookup"><span data-stu-id="c23d7-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="c23d7-108">[in] Имя назначения экспорта метода в неуправляемой библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="c23d7-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="c23d7-109">[in] Токен для целевого DLL в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="c23d7-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c23d7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c23d7-110">Requirements</span></span>  
 <span data-ttu-id="c23d7-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c23d7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c23d7-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c23d7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c23d7-113">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c23d7-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c23d7-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c23d7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c23d7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c23d7-115">See Also</span></span>  
 [<span data-ttu-id="c23d7-116">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c23d7-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="c23d7-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c23d7-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
