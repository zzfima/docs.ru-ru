---
title: Метод IMetaDataImport::GetPropertyProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08bd5beeb9fab1cd5b703c3afc4e82aaf71dbbc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122607"
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="e576c-102">Метод IMetaDataImport::GetPropertyProps</span><span class="sxs-lookup"><span data-stu-id="e576c-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="e576c-103">Получает метаданные для свойства, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="e576c-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e576c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e576c-104">Syntax</span></span>  
  
```  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,   
   [out] LPCWSTR           szProperty,   
   [in]  ULONG             cchProperty,   
   [out] ULONG             *pchProperty,   
   [out] DWORD             *pdwPropFlags,   
   [out] PCCOR_SIGNATURE   *ppvSig,   
   [out] ULONG             *pbSig,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,   
   [out] mdMethodDef       *pmdGetter,   
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,   
   [out] ULONG             *pcOtherMethod   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e576c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e576c-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="e576c-106">[in] Токен, который представляет свойство для возврата метаданных.</span><span class="sxs-lookup"><span data-stu-id="e576c-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="e576c-107">[out] Указатель на токен TypeDef, представляющий тип, реализующий свойства.</span><span class="sxs-lookup"><span data-stu-id="e576c-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="e576c-108">[out] Буфер для хранения имени свойства.</span><span class="sxs-lookup"><span data-stu-id="e576c-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="e576c-109">[in] Размер в расширенных символах `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="e576c-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="e576c-110">[out] Число расширенных символов, возвращаемых в `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="e576c-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="e576c-111">[out] Указатель на любой флаги атрибутов, примененным к свойству.</span><span class="sxs-lookup"><span data-stu-id="e576c-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="e576c-112">Это значение является битовой [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="e576c-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="e576c-113">[out] Указатель на подпись метаданных свойства.</span><span class="sxs-lookup"><span data-stu-id="e576c-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="e576c-114">[out] Число байтов, возвращаемых в `ppvSig`.</span><span class="sxs-lookup"><span data-stu-id="e576c-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="e576c-115">[out] Флаг, указывающий тип константы, которая является значением по умолчанию свойства.</span><span class="sxs-lookup"><span data-stu-id="e576c-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="e576c-116">Это значение равно из CorElementType перечисления.</span><span class="sxs-lookup"><span data-stu-id="e576c-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="e576c-117">[out] Указатель на байты, которые хранят значение по умолчанию для этого свойства.</span><span class="sxs-lookup"><span data-stu-id="e576c-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="e576c-118">[out] Размер в расширенных символах `ppDefaultValue`, если `pdwCPlusTypeFlag` является соответствующим; в противном случае это значение неприменимо.</span><span class="sxs-lookup"><span data-stu-id="e576c-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="e576c-119">В этом случае длина `ppDefaultValue` выводится из типа, который задается параметром `pdwCPlusTypeFlag`.</span><span class="sxs-lookup"><span data-stu-id="e576c-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="e576c-120">[out] Указатель на токен MethodDef, представляющий метод доступа set для свойства.</span><span class="sxs-lookup"><span data-stu-id="e576c-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="e576c-121">[out] Указатель на токен MethodDef, представляющий метод доступа get свойства.</span><span class="sxs-lookup"><span data-stu-id="e576c-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="e576c-122">[out] Массив токены MethodDef, представляющие другие методы, связанные со свойством.</span><span class="sxs-lookup"><span data-stu-id="e576c-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e576c-123">[in] Максимальный размер массива `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="e576c-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="e576c-124">Если вы не укажете массив недостаточно велик для хранения всех методов, они пропускаются без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="e576c-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="e576c-125">[out] Количество токены MethodDef, возвращаемых в `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="e576c-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e576c-126">Требования</span><span class="sxs-lookup"><span data-stu-id="e576c-126">Requirements</span></span>  
 <span data-ttu-id="e576c-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e576c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e576c-128">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e576c-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e576c-129">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e576c-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e576c-130">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e576c-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e576c-131">См. также</span><span class="sxs-lookup"><span data-stu-id="e576c-131">See also</span></span>

- [<span data-ttu-id="e576c-132">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e576c-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e576c-133">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e576c-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
