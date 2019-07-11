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
ms.openlocfilehash: c714915651d8660a739d8ee6518fc3814af4c08d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782417"
---
# <a name="imetadataimportgetcustomattributeprops-method"></a><span data-ttu-id="5af94-102">Метод IMetaDataImport::GetCustomAttributeProps</span><span class="sxs-lookup"><span data-stu-id="5af94-102">IMetaDataImport::GetCustomAttributeProps Method</span></span>
<span data-ttu-id="5af94-103">Возвращает значение пользовательского атрибута по указанному токену метаданных.</span><span class="sxs-lookup"><span data-stu-id="5af94-103">Gets the value of the custom attribute, given its metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5af94-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5af94-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5af94-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5af94-105">Parameters</span></span>  
 `cv`  
 <span data-ttu-id="5af94-106">[in] Токен метаданных, который представляет извлекаемый пользовательский атрибут.</span><span class="sxs-lookup"><span data-stu-id="5af94-106">[in] A metadata token that represents the custom attribute to be retrieved.</span></span>  
  
 `ptkObj`  
 <span data-ttu-id="5af94-107">[out, optional] Токен метаданных, представляющий объект, который изменяет пользовательский атрибут.</span><span class="sxs-lookup"><span data-stu-id="5af94-107">[out, optional] A metadata token representing the object that the custom attribute modifies.</span></span> <span data-ttu-id="5af94-108">Это значение может быть любым типом токена метаданных, кроме `mdCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="5af94-108">This value can be any type of metadata token except `mdCustomAttribute`.</span></span>  
  
 `ptkType`  
 <span data-ttu-id="5af94-109">[out, optional] Токен метаданных `mdMethodDef` или `mdMemberRef`, представляющий <xref:System.Type> возвращаемого пользовательского атрибута.</span><span class="sxs-lookup"><span data-stu-id="5af94-109">[out, optional] An `mdMethodDef` or `mdMemberRef` metadata token representing the <xref:System.Type> of the returned custom attribute.</span></span>  
  
 `ppBlob`  
 <span data-ttu-id="5af94-110">[out, optional] Указатель на массив данных, который является значением пользовательского атрибута.</span><span class="sxs-lookup"><span data-stu-id="5af94-110">[out, optional] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="5af94-111">[out, optional] Размер в байтах данных, возвращаемых в \*`ppBlob`.</span><span class="sxs-lookup"><span data-stu-id="5af94-111">[out, optional] The size in bytes of the data returned in \*`ppBlob`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5af94-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="5af94-112">Remarks</span></span>  
 <span data-ttu-id="5af94-113">Пользовательский атрибут хранится в виде массива данных, в формате, который поддерживается подсистемой метаданных.</span><span class="sxs-lookup"><span data-stu-id="5af94-113">A custom attribute is stored as an array of data, the format which is understood by the metadata engine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5af94-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5af94-114">Requirements</span></span>  
 <span data-ttu-id="5af94-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5af94-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5af94-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5af94-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5af94-117">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5af94-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5af94-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5af94-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5af94-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5af94-119">See also</span></span>

- [<span data-ttu-id="5af94-120">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5af94-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5af94-121">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5af94-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
