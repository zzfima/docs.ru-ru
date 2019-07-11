---
title: Метод IMetaDataImport::GetPinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e1be6079ed382b8ab27d0aec16bd725f5c5b9cb5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778902"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="7c1c8-102">Метод IMetaDataImport::GetPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="7c1c8-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="7c1c8-103">Возвращает токен ModuleRef, представляющий целевую сборку вызова PInvoke.</span><span class="sxs-lookup"><span data-stu-id="7c1c8-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c1c8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c1c8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c1c8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7c1c8-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="7c1c8-106">[in] Токен FieldDef или MethodDef, чтобы получить метаданные сопоставления PInvoke для.</span><span class="sxs-lookup"><span data-stu-id="7c1c8-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="7c1c8-107">[out] Указатель на флаги, используемые для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="7c1c8-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="7c1c8-108">Это значение является битовой [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="7c1c8-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="7c1c8-109">[out] Имя целевой неуправляемой библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="7c1c8-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="7c1c8-110">[in] Размер в расширенных символах `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="7c1c8-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="7c1c8-111">[out] Число расширенных символов, возвращаемых в `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="7c1c8-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="7c1c8-112">[out] Указатель на токен ModuleRef, представляющий неуправляемый целевой объект библиотеки.</span><span class="sxs-lookup"><span data-stu-id="7c1c8-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c1c8-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7c1c8-113">Requirements</span></span>  
 <span data-ttu-id="7c1c8-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c1c8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c1c8-115">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7c1c8-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c1c8-116">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c1c8-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7c1c8-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c1c8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c1c8-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7c1c8-118">See also</span></span>

- [<span data-ttu-id="7c1c8-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="7c1c8-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7c1c8-120">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="7c1c8-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
