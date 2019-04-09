---
title: Метод IMetaDataImport::GetCustomAttributeByName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 61029074347d554faaefe790c1e408e860e34690
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183031"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="f0a51-102">Метод IMetaDataImport::GetCustomAttributeByName</span><span class="sxs-lookup"><span data-stu-id="f0a51-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="f0a51-103">Получает настраиваемый атрибут, учитывая его название и владельца.</span><span class="sxs-lookup"><span data-stu-id="f0a51-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0a51-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0a51-104">Syntax</span></span>  
  
```  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0a51-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0a51-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="f0a51-106">[in] Токен метаданных, представляющий объект, которому принадлежит настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="f0a51-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="f0a51-107">[in] Имя настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="f0a51-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="f0a51-108">[out] Указатель на массив данных, который является значением настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="f0a51-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="f0a51-109">[out] Размер в байтах данных, возвращаемых в \*`ppData`.</span><span class="sxs-lookup"><span data-stu-id="f0a51-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0a51-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0a51-110">Remarks</span></span>  
 <span data-ttu-id="f0a51-111">Можно определить несколько настраиваемых атрибутов для того же владельца; они могут даже совпадать.</span><span class="sxs-lookup"><span data-stu-id="f0a51-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="f0a51-112">Тем не менее `GetCustomAttributeByName` возвращает только один экземпляр.</span><span class="sxs-lookup"><span data-stu-id="f0a51-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="f0a51-113">(`GetCustomAttributeByName` возвращает первый обнаруженный экземпляр.) Чтобы найти все экземпляры настраиваемого атрибута, вызовите [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="f0a51-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0a51-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f0a51-114">Requirements</span></span>  
 <span data-ttu-id="f0a51-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0a51-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0a51-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f0a51-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f0a51-117">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f0a51-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f0a51-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f0a51-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f0a51-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f0a51-119">See also</span></span>

- [<span data-ttu-id="f0a51-120">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f0a51-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f0a51-121">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f0a51-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
