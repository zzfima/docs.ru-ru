---
title: Метод IMetaDataImport::GetScopeProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
ms.openlocfilehash: af1c3d599c5280e584ffb842c96c70a7c3d4ed08
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436880"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="6d326-102">Метод IMetaDataImport::GetScopeProps</span><span class="sxs-lookup"><span data-stu-id="6d326-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="6d326-103">Возвращает имя и при необходимости идентификатор версии сборки или модуля в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="6d326-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d326-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d326-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d326-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d326-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="6d326-106">заполняет Буфер для имени сборки или модуля.</span><span class="sxs-lookup"><span data-stu-id="6d326-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="6d326-107">окне Размер в расширенных символах `szName`.</span><span class="sxs-lookup"><span data-stu-id="6d326-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="6d326-108">заполняет Число расширенных символов, возвращаемых в `szName`.</span><span class="sxs-lookup"><span data-stu-id="6d326-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="6d326-109">[out, необязательно] Указатель на идентификатор GUID, однозначно определяющий версию сборки или модуля.</span><span class="sxs-lookup"><span data-stu-id="6d326-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d326-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="6d326-110">Remarks</span></span>  
 <span data-ttu-id="6d326-111">Для задания этих свойств используется метод [IMetaDataEmit:: сетмодулепропс](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6d326-111">The [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d326-112">Требования</span><span class="sxs-lookup"><span data-stu-id="6d326-112">Requirements</span></span>  
 <span data-ttu-id="6d326-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d326-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d326-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="6d326-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d326-115">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6d326-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d326-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d326-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d326-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="6d326-117">See also</span></span>

- [<span data-ttu-id="6d326-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6d326-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6d326-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6d326-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
