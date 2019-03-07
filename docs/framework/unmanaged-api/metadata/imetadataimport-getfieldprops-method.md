---
title: Метод IMetaDataImport::GetFieldProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1064300d8bb3a9b03e1dfad1c30596c35ee1c941
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485204"
---
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="38217-102">Метод IMetaDataImport::GetFieldProps</span><span class="sxs-lookup"><span data-stu-id="38217-102">IMetaDataImport::GetFieldProps Method</span></span>
<span data-ttu-id="38217-103">Возвращает метаданные, связанные с полем, на которое ссылается указанный токен FieldDef.</span><span class="sxs-lookup"><span data-stu-id="38217-103">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38217-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38217-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="38217-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="38217-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="38217-106">[in] Токен FieldDef, который представляет связанные метаданные для поля.</span><span class="sxs-lookup"><span data-stu-id="38217-106">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="38217-107">[out] Указатель на токен TypeDef, представляющий тип класса, которой принадлежит это поле.</span><span class="sxs-lookup"><span data-stu-id="38217-107">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="38217-108">[out] Имя поля.</span><span class="sxs-lookup"><span data-stu-id="38217-108">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="38217-109">[in] Размер в расширенных символах, буфера для *szField*.</span><span class="sxs-lookup"><span data-stu-id="38217-109">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="38217-110">[out] Фактический размер возвращенного буфера.</span><span class="sxs-lookup"><span data-stu-id="38217-110">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="38217-111">[out] Флаги, связанные с метаданными поля.</span><span class="sxs-lookup"><span data-stu-id="38217-111">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="38217-112">[in] Указатель на значение двоичных метаданных, описывающий поле.</span><span class="sxs-lookup"><span data-stu-id="38217-112">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="38217-113">[out] Размер в байтах `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="38217-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="38217-114">[out] Флаг, указывающий тип значения поля.</span><span class="sxs-lookup"><span data-stu-id="38217-114">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="38217-115">[out] Постоянное значение для поля.</span><span class="sxs-lookup"><span data-stu-id="38217-115">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="38217-116">[out] Размер в символы `ppValue`, или нуль, если строка не существует.</span><span class="sxs-lookup"><span data-stu-id="38217-116">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38217-117">Требования</span><span class="sxs-lookup"><span data-stu-id="38217-117">Requirements</span></span>  
 <span data-ttu-id="38217-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38217-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38217-119">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="38217-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38217-120">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38217-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38217-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38217-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38217-122">См. также</span><span class="sxs-lookup"><span data-stu-id="38217-122">See also</span></span>
- [<span data-ttu-id="38217-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="38217-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="38217-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="38217-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
