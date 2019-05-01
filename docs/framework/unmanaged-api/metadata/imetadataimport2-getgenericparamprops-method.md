---
title: Метод IMetaDataImport2::GetGenericParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 55a765fe3942cbf71a8460187e829dc7f3ca877e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049860"
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="d0995-102">Метод IMetaDataImport2::GetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="d0995-102">IMetaDataImport2::GetGenericParamProps Method</span></span>
<span data-ttu-id="d0995-103">Получает метаданные, связанные с универсального параметра, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="d0995-103">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0995-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0995-104">Syntax</span></span>  
  
```  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0995-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d0995-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="d0995-106">[in] Токен, представляющий универсальный параметр, для которого необходимо вернуть метаданные.</span><span class="sxs-lookup"><span data-stu-id="d0995-106">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="d0995-107">[out] Порядковый номер `Type` параметра в родительский конструктор или метод.</span><span class="sxs-lookup"><span data-stu-id="d0995-107">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="d0995-108">[out] Значение [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) перечисление, описывающее `Type` универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="d0995-108">[out] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="d0995-109">[out] TypeDef или MethodDef токен, представляющий владельца параметра.</span><span class="sxs-lookup"><span data-stu-id="d0995-109">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="d0995-110">[out] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="d0995-110">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="d0995-111">[out] Имя универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="d0995-111">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d0995-112">[in] Размер `wzName` буфера.</span><span class="sxs-lookup"><span data-stu-id="d0995-112">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="d0995-113">[out] Возвращаемый размер имени, в расширенных символах.</span><span class="sxs-lookup"><span data-stu-id="d0995-113">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0995-114">Требования</span><span class="sxs-lookup"><span data-stu-id="d0995-114">Requirements</span></span>  
 <span data-ttu-id="d0995-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0995-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0995-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d0995-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d0995-117">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d0995-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d0995-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0995-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0995-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d0995-119">See also</span></span>

- [<span data-ttu-id="d0995-120">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d0995-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="d0995-121">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d0995-121">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
