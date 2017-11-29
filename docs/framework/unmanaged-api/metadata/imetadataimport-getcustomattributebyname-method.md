---
title: "Метод IMetaDataImport::GetCustomAttributeByName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetCustomAttributeByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5b689c54b5e8d741d32bc941b4e78e6674f15e01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="8b251-102">Метод IMetaDataImport::GetCustomAttributeByName</span><span class="sxs-lookup"><span data-stu-id="8b251-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="8b251-103">Получает настраиваемый атрибут, ее имя и владельца.</span><span class="sxs-lookup"><span data-stu-id="8b251-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b251-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b251-104">Syntax</span></span>  
  
```  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b251-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8b251-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="8b251-106">[in] Токен метаданных, представляющий объект, которому принадлежит пользовательский атрибут.</span><span class="sxs-lookup"><span data-stu-id="8b251-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="8b251-107">[in] Имя настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="8b251-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="8b251-108">[out] Указатель на массив данных, который является значением настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="8b251-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="8b251-109">[out] Размер в байтах данных, возвращаемых в *`ppData`.</span><span class="sxs-lookup"><span data-stu-id="8b251-109">[out] The size in bytes of the data returned in *`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b251-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="8b251-110">Remarks</span></span>  
 <span data-ttu-id="8b251-111">Можно определить несколько настраиваемых атрибутов для того же владельца; они могут даже имеют то же имя.</span><span class="sxs-lookup"><span data-stu-id="8b251-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="8b251-112">Тем не менее `GetCustomAttributeByName` возвращает только один экземпляр.</span><span class="sxs-lookup"><span data-stu-id="8b251-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="8b251-113">(`GetCustomAttributeByName` возвращает первый экземпляр, расположенного.) Чтобы найти все вхождения настраиваемый атрибут, вызовите [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="8b251-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b251-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8b251-114">Requirements</span></span>  
 <span data-ttu-id="8b251-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b251-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b251-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8b251-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8b251-117">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b251-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8b251-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b251-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b251-119">См. также</span><span class="sxs-lookup"><span data-stu-id="8b251-119">See Also</span></span>  
 [<span data-ttu-id="8b251-120">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8b251-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="8b251-121">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8b251-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
