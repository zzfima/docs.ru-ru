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
ms.openlocfilehash: 9a80336db4a5a8d7cfdebb7eb8d25bcb8f96e87c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437646"
---
# <a name="imetadataimportgetcustomattributeprops-method"></a><span data-ttu-id="ebf1e-102">Метод IMetaDataImport::GetCustomAttributeProps</span><span class="sxs-lookup"><span data-stu-id="ebf1e-102">IMetaDataImport::GetCustomAttributeProps Method</span></span>
<span data-ttu-id="ebf1e-103">Возвращает значение пользовательского атрибута по указанному токену метаданных.</span><span class="sxs-lookup"><span data-stu-id="ebf1e-103">Gets the value of the custom attribute, given its metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebf1e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebf1e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebf1e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ebf1e-105">Parameters</span></span>  
 `cv`  
 <span data-ttu-id="ebf1e-106">[in] Токен метаданных, который представляет извлекаемый пользовательский атрибут.</span><span class="sxs-lookup"><span data-stu-id="ebf1e-106">[in] A metadata token that represents the custom attribute to be retrieved.</span></span>  
  
 `ptkObj`  
 <span data-ttu-id="ebf1e-107">[out, optional] Токен метаданных, представляющий объект, который изменяет пользовательский атрибут.</span><span class="sxs-lookup"><span data-stu-id="ebf1e-107">[out, optional] A metadata token representing the object that the custom attribute modifies.</span></span> <span data-ttu-id="ebf1e-108">Это значение может быть любым типом токена метаданных, кроме `mdCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="ebf1e-108">This value can be any type of metadata token except `mdCustomAttribute`.</span></span>  
  
 `ptkType`  
 <span data-ttu-id="ebf1e-109">[out, optional] Токен метаданных `mdMethodDef` или `mdMemberRef`, представляющий <xref:System.Type> возвращаемого пользовательского атрибута.</span><span class="sxs-lookup"><span data-stu-id="ebf1e-109">[out, optional] An `mdMethodDef` or `mdMemberRef` metadata token representing the <xref:System.Type> of the returned custom attribute.</span></span>  
  
 `ppBlob`  
 <span data-ttu-id="ebf1e-110">[out, optional] Указатель на массив данных, который является значением пользовательского атрибута.</span><span class="sxs-lookup"><span data-stu-id="ebf1e-110">[out, optional] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="ebf1e-111">[out, optional] Размер в байтах данных, возвращаемых в \*`ppBlob`.</span><span class="sxs-lookup"><span data-stu-id="ebf1e-111">[out, optional] The size in bytes of the data returned in \*`ppBlob`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebf1e-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="ebf1e-112">Remarks</span></span>  
 <span data-ttu-id="ebf1e-113">Пользовательский атрибут хранится в виде массива данных, в формате, который поддерживается подсистемой метаданных.</span><span class="sxs-lookup"><span data-stu-id="ebf1e-113">A custom attribute is stored as an array of data, the format which is understood by the metadata engine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebf1e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ebf1e-114">Requirements</span></span>  
 <span data-ttu-id="ebf1e-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebf1e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebf1e-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ebf1e-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ebf1e-117">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ebf1e-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ebf1e-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebf1e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebf1e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ebf1e-119">See also</span></span>

- [<span data-ttu-id="ebf1e-120">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ebf1e-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ebf1e-121">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ebf1e-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
