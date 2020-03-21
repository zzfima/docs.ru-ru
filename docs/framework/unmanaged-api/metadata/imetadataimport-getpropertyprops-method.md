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
ms.openlocfilehash: 5fc71bf240b89afadbf8f2ba10906322921bdda2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175334"
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="4bf29-102">Метод IMetaDataImport::GetPropertyProps</span><span class="sxs-lookup"><span data-stu-id="4bf29-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="4bf29-103">Получает метаданные для свойства, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="4bf29-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bf29-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4bf29-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="4bf29-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4bf29-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="4bf29-106">(в) Токен, представляющий свойство для возврата метаданных.</span><span class="sxs-lookup"><span data-stu-id="4bf29-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="4bf29-107">(ваут) Указатель на маркер TypeDef, представляющий тип, реализуемый в свойстве.</span><span class="sxs-lookup"><span data-stu-id="4bf29-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="4bf29-108">(ваут) Буфер для удержания имени свойства.</span><span class="sxs-lookup"><span data-stu-id="4bf29-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="4bf29-109">(в) Размер в широких `szProperty`символов .</span><span class="sxs-lookup"><span data-stu-id="4bf29-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="4bf29-110">(ваут) Количество широких символов `szProperty`вернулся в .</span><span class="sxs-lookup"><span data-stu-id="4bf29-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="4bf29-111">(ваут) Указатель на любые атрибуты флаги, применяемые к свойству.</span><span class="sxs-lookup"><span data-stu-id="4bf29-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="4bf29-112">Это значение битмаска из [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="4bf29-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="4bf29-113">(ваут) Указатель на подпись метаданных свойства.</span><span class="sxs-lookup"><span data-stu-id="4bf29-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="4bf29-114">(ваут) Количество байтов вернулось в `ppvSig`.</span><span class="sxs-lookup"><span data-stu-id="4bf29-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="4bf29-115">(ваут) Флаг, определяющий тип константы, которая является значением свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4bf29-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="4bf29-116">Это значение из перечисления CorElementType.</span><span class="sxs-lookup"><span data-stu-id="4bf29-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="4bf29-117">(ваут) Указатель на байты, которые хранят значение по умолчанию для этого свойства.</span><span class="sxs-lookup"><span data-stu-id="4bf29-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="4bf29-118">(ваут) Размер в широких `ppDefaultValue`символов, если `pdwCPlusTypeFlag` это ELEMENT_TYPE_STRING; в противном случае это значение не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="4bf29-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="4bf29-119">В этом случае длина `ppDefaultValue` выводилась из типа, `pdwCPlusTypeFlag`указанного .</span><span class="sxs-lookup"><span data-stu-id="4bf29-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="4bf29-120">(ваут) Указатель на маркер MethodDef, представляющий метод набора доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="4bf29-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="4bf29-121">(ваут) Указатель на токен MethodDef, представляющий метод получения доступа к свойству.</span><span class="sxs-lookup"><span data-stu-id="4bf29-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="4bf29-122">(ваут) Массив токенов MethodDef, представляющих другие методы, связанные с свойством.</span><span class="sxs-lookup"><span data-stu-id="4bf29-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4bf29-123">[in] Максимальный размер массива `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="4bf29-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="4bf29-124">Если вы не предоставляете массив достаточно большой, чтобы держать все методы, они пропущены без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="4bf29-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="4bf29-125">(ваут) Количество возвращенных токенов MethodDef `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="4bf29-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bf29-126">Требования</span><span class="sxs-lookup"><span data-stu-id="4bf29-126">Requirements</span></span>  
 <span data-ttu-id="4bf29-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bf29-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bf29-128">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4bf29-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4bf29-129">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4bf29-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4bf29-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bf29-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bf29-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4bf29-131">See also</span></span>

- [<span data-ttu-id="4bf29-132">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4bf29-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4bf29-133">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4bf29-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
