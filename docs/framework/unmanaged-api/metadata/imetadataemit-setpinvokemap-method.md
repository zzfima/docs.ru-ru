---
title: Метод IMetaDataEmit::SetPinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84b2c0571a7991829e65b45759bd61fa4009aa71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445881"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="a367e-102">Метод IMetaDataEmit::SetPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="a367e-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="a367e-103">Задает или изменяет функции сигнатуры PInvoke метода, в соответствии с определением предыдущего вызова [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="a367e-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a367e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a367e-104">Syntax</span></span>  
  
```  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a367e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a367e-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="a367e-106">[in] `mdToken` Какие сопоставление информация относится.</span><span class="sxs-lookup"><span data-stu-id="a367e-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="a367e-107">[in] Флаги, используемые для сопоставления PInvoke.</span><span class="sxs-lookup"><span data-stu-id="a367e-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="a367e-108">Это битовая маска `CorPinvokeMap` значения.</span><span class="sxs-lookup"><span data-stu-id="a367e-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="a367e-109">[in] Имя целевого объекта экспорта в DLL с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="a367e-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="a367e-110">[in] `mdModuleRef` Маркеров для целевого объекта неуправляемые библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="a367e-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a367e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a367e-111">Requirements</span></span>  
 <span data-ttu-id="a367e-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a367e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a367e-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a367e-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a367e-114">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a367e-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a367e-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a367e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a367e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a367e-116">See Also</span></span>  
 [<span data-ttu-id="a367e-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a367e-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="a367e-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a367e-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
