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
ms.openlocfilehash: 8c3f98a124dbbcae3b0500932a2357ed1757951f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177238"
---
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="9d95f-102">Метод IMetaDataImport::GetFieldProps</span><span class="sxs-lookup"><span data-stu-id="9d95f-102">IMetaDataImport::GetFieldProps Method</span></span>
<span data-ttu-id="9d95f-103">Возвращает метаданные, связанные с полем, на которое ссылается указанный токен FieldDef.</span><span class="sxs-lookup"><span data-stu-id="9d95f-103">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d95f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d95f-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="9d95f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d95f-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="9d95f-106">(в) Токен FieldDef, представляющий поле для получения связанных метаданных.</span><span class="sxs-lookup"><span data-stu-id="9d95f-106">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="9d95f-107">(ваут) Указатель на маркер TypeDef, представляющий тип класса, к которому принадлежит поле.</span><span class="sxs-lookup"><span data-stu-id="9d95f-107">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="9d95f-108">(ваут) Название поля.</span><span class="sxs-lookup"><span data-stu-id="9d95f-108">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="9d95f-109">(в) Размер в широких символах буфера для *szField*.</span><span class="sxs-lookup"><span data-stu-id="9d95f-109">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="9d95f-110">(ваут) Фактический размер возвращенного буфера.</span><span class="sxs-lookup"><span data-stu-id="9d95f-110">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="9d95f-111">(ваут) Флаги, связанные с метаданными поля.</span><span class="sxs-lookup"><span data-stu-id="9d95f-111">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="9d95f-112">(в) Указатель на двоичное значение метаданных, описывающий поле.</span><span class="sxs-lookup"><span data-stu-id="9d95f-112">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="9d95f-113">(ваут) Размер байтов `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="9d95f-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="9d95f-114">(ваут) Флаг, описавательный тип значения поля.</span><span class="sxs-lookup"><span data-stu-id="9d95f-114">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="9d95f-115">(ваут) Постоянное значение для поля.</span><span class="sxs-lookup"><span data-stu-id="9d95f-115">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="9d95f-116">(ваут) Размер в символах, или ноль, если строка `ppValue`не существует.</span><span class="sxs-lookup"><span data-stu-id="9d95f-116">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d95f-117">Требования</span><span class="sxs-lookup"><span data-stu-id="9d95f-117">Requirements</span></span>  
 <span data-ttu-id="9d95f-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d95f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d95f-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9d95f-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d95f-120">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9d95f-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9d95f-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d95f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d95f-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9d95f-122">See also</span></span>

- [<span data-ttu-id="9d95f-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="9d95f-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9d95f-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="9d95f-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
