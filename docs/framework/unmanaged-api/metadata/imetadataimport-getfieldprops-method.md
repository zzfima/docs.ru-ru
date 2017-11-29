---
title: "Метод IMetaDataImport::GetFieldProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetFieldProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d5874169e0f8c452b177309702444ea84858557e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="4334a-102">Метод IMetaDataImport::GetFieldProps</span><span class="sxs-lookup"><span data-stu-id="4334a-102">IMetaDataImport::GetFieldProps Method</span></span>
<span data-ttu-id="4334a-103">Возвращает метаданные, связанные с полем, на которое ссылается указанный токен FieldDef.</span><span class="sxs-lookup"><span data-stu-id="4334a-103">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4334a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4334a-104">Syntax</span></span>  
  
```  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,   
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4334a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4334a-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="4334a-106">[in] Представляющий поле, чтобы получить связанные метаданные для токен FieldDef.</span><span class="sxs-lookup"><span data-stu-id="4334a-106">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="4334a-107">[out] Указатель на токен TypeDef, представляющий тип класса, к которому принадлежит поле.</span><span class="sxs-lookup"><span data-stu-id="4334a-107">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="4334a-108">[out] Имя поля.</span><span class="sxs-lookup"><span data-stu-id="4334a-108">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="4334a-109">[in] Размер в расширенных символах, буфера для *szField*.</span><span class="sxs-lookup"><span data-stu-id="4334a-109">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="4334a-110">[out] Фактический размер возвращенного буфера.</span><span class="sxs-lookup"><span data-stu-id="4334a-110">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="4334a-111">[out] Флаги, связанные с поля метаданных.</span><span class="sxs-lookup"><span data-stu-id="4334a-111">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="4334a-112">[in] Указатель на значение двоичного метаданных с описанием поля.</span><span class="sxs-lookup"><span data-stu-id="4334a-112">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="4334a-113">[out] Размер в байтах `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="4334a-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="4334a-114">[out] Флаг, указывающий тип значения поля.</span><span class="sxs-lookup"><span data-stu-id="4334a-114">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="4334a-115">[out] Постоянное значение для поля.</span><span class="sxs-lookup"><span data-stu-id="4334a-115">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="4334a-116">[out] Размер в символах для `ppValue`, или нуль, если строка не существует.</span><span class="sxs-lookup"><span data-stu-id="4334a-116">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4334a-117">Требования</span><span class="sxs-lookup"><span data-stu-id="4334a-117">Requirements</span></span>  
 <span data-ttu-id="4334a-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4334a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4334a-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4334a-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4334a-120">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4334a-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4334a-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4334a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4334a-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4334a-122">See Also</span></span>  
 [<span data-ttu-id="4334a-123">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4334a-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="4334a-124">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4334a-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
