---
title: Метод IMetaDataImport::GetCustomAttributeProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeProps
helpviewer_keywords:
- GetCustomAttributeProps method [.NET Framework metadata]
- IMetaDataImport::GetCustomAttributeProps method [.NET Framework metadata]
ms.assetid: 6eefb243-a281-41c1-bcdc-7e17513bc446
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c27a55166ebc055f324ec45ba6dfd835c8b8bbf6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075747"
---
# <a name="imetadataimportgetcustomattributeprops-method"></a><span data-ttu-id="d8dbf-102">Метод IMetaDataImport::GetCustomAttributeProps</span><span class="sxs-lookup"><span data-stu-id="d8dbf-102">IMetaDataImport::GetCustomAttributeProps Method</span></span>
<span data-ttu-id="d8dbf-103">Возвращает значение пользовательского атрибута по указанному токену метаданных.</span><span class="sxs-lookup"><span data-stu-id="d8dbf-103">Gets the value of the custom attribute, given its metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8dbf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8dbf-104">Syntax</span></span>  
  
```  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8dbf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d8dbf-105">Parameters</span></span>  
 `cv`  
 <span data-ttu-id="d8dbf-106">[in] Токен метаданных, который представляет извлекаемый пользовательский атрибут.</span><span class="sxs-lookup"><span data-stu-id="d8dbf-106">[in] A metadata token that represents the custom attribute to be retrieved.</span></span>  
  
 `ptkObj`  
 <span data-ttu-id="d8dbf-107">[out, optional] Токен метаданных, представляющий объект, который изменяет пользовательский атрибут.</span><span class="sxs-lookup"><span data-stu-id="d8dbf-107">[out, optional] A metadata token representing the object that the custom attribute modifies.</span></span> <span data-ttu-id="d8dbf-108">Это значение может быть любым типом токена метаданных, кроме `mdCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="d8dbf-108">This value can be any type of metadata token except `mdCustomAttribute`.</span></span>  
  
 `ptkType`  
 <span data-ttu-id="d8dbf-109">[out, optional] Токен метаданных `mdMethodDef` или `mdMemberRef`, представляющий <xref:System.Type> возвращаемого пользовательского атрибута.</span><span class="sxs-lookup"><span data-stu-id="d8dbf-109">[out, optional] An `mdMethodDef` or `mdMemberRef` metadata token representing the <xref:System.Type> of the returned custom attribute.</span></span>  
  
 `ppBlob`  
 <span data-ttu-id="d8dbf-110">[out, optional] Указатель на массив данных, который является значением пользовательского атрибута.</span><span class="sxs-lookup"><span data-stu-id="d8dbf-110">[out, optional] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="d8dbf-111">[out, optional] Размер в байтах данных, возвращаемых в \*`ppBlob`.</span><span class="sxs-lookup"><span data-stu-id="d8dbf-111">[out, optional] The size in bytes of the data returned in \*`ppBlob`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8dbf-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="d8dbf-112">Remarks</span></span>  
 <span data-ttu-id="d8dbf-113">Пользовательский атрибут хранится в виде массива данных, в формате, который поддерживается подсистемой метаданных.</span><span class="sxs-lookup"><span data-stu-id="d8dbf-113">A custom attribute is stored as an array of data, the format which is understood by the metadata engine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8dbf-114">Требования</span><span class="sxs-lookup"><span data-stu-id="d8dbf-114">Requirements</span></span>  
 <span data-ttu-id="d8dbf-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8dbf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8dbf-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d8dbf-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d8dbf-117">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d8dbf-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d8dbf-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8dbf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8dbf-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d8dbf-119">See also</span></span>

- [<span data-ttu-id="d8dbf-120">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d8dbf-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d8dbf-121">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d8dbf-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
