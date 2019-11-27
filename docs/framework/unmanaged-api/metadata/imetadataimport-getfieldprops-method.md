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
ms.openlocfilehash: 462512fd2c2b33905b45bb67599b23b301fc71f7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437992"
---
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="b4fd0-102">Метод IMetaDataImport::GetFieldProps</span><span class="sxs-lookup"><span data-stu-id="b4fd0-102">IMetaDataImport::GetFieldProps Method</span></span>
<span data-ttu-id="b4fd0-103">Возвращает метаданные, связанные с полем, на которое ссылается указанный токен FieldDef.</span><span class="sxs-lookup"><span data-stu-id="b4fd0-103">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4fd0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4fd0-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b4fd0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4fd0-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="b4fd0-106">окне Токен FieldDef, представляющий поле, для которого нужно получить связанные метаданные.</span><span class="sxs-lookup"><span data-stu-id="b4fd0-106">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="b4fd0-107">заполняет Указатель на маркер TypeDef, представляющий тип класса, которому принадлежит поле.</span><span class="sxs-lookup"><span data-stu-id="b4fd0-107">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="b4fd0-108">заполняет Имя поля.</span><span class="sxs-lookup"><span data-stu-id="b4fd0-108">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="b4fd0-109">окне Размер в расширенных символах буфера для *сзфиелд*.</span><span class="sxs-lookup"><span data-stu-id="b4fd0-109">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="b4fd0-110">заполняет Фактический размер возвращаемого буфера.</span><span class="sxs-lookup"><span data-stu-id="b4fd0-110">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="b4fd0-111">заполняет Флаги, связанные с метаданными поля.</span><span class="sxs-lookup"><span data-stu-id="b4fd0-111">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="b4fd0-112">окне Указатель на двоичное значение метаданных, описывающее поле.</span><span class="sxs-lookup"><span data-stu-id="b4fd0-112">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="b4fd0-113">заполняет Размер в байтах `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="b4fd0-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="b4fd0-114">заполняет Флаг, указывающий тип значения поля.</span><span class="sxs-lookup"><span data-stu-id="b4fd0-114">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b4fd0-115">заполняет Постоянное значение для поля.</span><span class="sxs-lookup"><span data-stu-id="b4fd0-115">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="b4fd0-116">заполняет Размер в символах `ppValue`или нуль, если строка не существует.</span><span class="sxs-lookup"><span data-stu-id="b4fd0-116">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4fd0-117">Требования</span><span class="sxs-lookup"><span data-stu-id="b4fd0-117">Requirements</span></span>  
 <span data-ttu-id="b4fd0-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4fd0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4fd0-119">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="b4fd0-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4fd0-120">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b4fd0-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b4fd0-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4fd0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4fd0-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b4fd0-122">See also</span></span>

- [<span data-ttu-id="b4fd0-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b4fd0-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b4fd0-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b4fd0-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
