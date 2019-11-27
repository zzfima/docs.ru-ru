---
title: Метод IMetaDataImport::GetMemberProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
ms.openlocfilehash: bc5bbba2fa4a95955e52a2e083a2097178b5d96a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437518"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="1d27e-102">Метод IMetaDataImport::GetMemberProps</span><span class="sxs-lookup"><span data-stu-id="1d27e-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="1d27e-103">Возвращает сведения, хранящиеся в метаданных для указанного определения элемента, включая имя, двоичную подпись и относительный виртуальный адрес элемента <xref:System.Type>, на который ссылается указанный маркер метаданных.</span><span class="sxs-lookup"><span data-stu-id="1d27e-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="1d27e-104">Это простой вспомогательный метод: Если *МБ* является MethodDef, то вызывается **жетмесодпропс** . Если *МБ* является FieldDef, вызывается **жетфиелдпропс** .</span><span class="sxs-lookup"><span data-stu-id="1d27e-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="1d27e-105">Дополнительные сведения см. в этих других методах.</span><span class="sxs-lookup"><span data-stu-id="1d27e-105">See these other methods for details.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="1d27e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d27e-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] ULONG             *pulCodeRVA,   
   [out] DWORD             *pdwImplFlags,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d27e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="1d27e-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="1d27e-108">окне Токен, ссылающийся на элемент, для которого необходимо получить связанные метаданные.</span><span class="sxs-lookup"><span data-stu-id="1d27e-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="1d27e-109">заполняет Указатель на маркер метаданных, представляющий класс члена.</span><span class="sxs-lookup"><span data-stu-id="1d27e-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="1d27e-110">заполняет Имя элемента.</span><span class="sxs-lookup"><span data-stu-id="1d27e-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="1d27e-111">окне Размер в расширенных символах буфера `szMember`.</span><span class="sxs-lookup"><span data-stu-id="1d27e-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="1d27e-112">заполняет Размер в расширенных символах возвращаемого имени.</span><span class="sxs-lookup"><span data-stu-id="1d27e-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="1d27e-113">заполняет Все значения флагов, примененные к элементу.</span><span class="sxs-lookup"><span data-stu-id="1d27e-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="1d27e-114">заполняет Указатель на сигнатуру двоичных метаданных элемента.</span><span class="sxs-lookup"><span data-stu-id="1d27e-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="1d27e-115">заполняет Размер в байтах `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="1d27e-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="1d27e-116">заполняет Указатель на относительный виртуальный адрес элемента.</span><span class="sxs-lookup"><span data-stu-id="1d27e-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="1d27e-117">заполняет Любые флаги реализации метода, связанные с элементом.</span><span class="sxs-lookup"><span data-stu-id="1d27e-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="1d27e-118">заполняет Флаг, помечающий <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="1d27e-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="1d27e-119">Это одно из значений `ELEMENT_TYPE_*`.</span><span class="sxs-lookup"><span data-stu-id="1d27e-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="1d27e-120">заполняет Константное строковое значение, возвращаемое этим элементом.</span><span class="sxs-lookup"><span data-stu-id="1d27e-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="1d27e-121">заполняет Размер в символах `ppValue`или нуль, если `ppValue` не содержит строку.</span><span class="sxs-lookup"><span data-stu-id="1d27e-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d27e-122">Требования</span><span class="sxs-lookup"><span data-stu-id="1d27e-122">Requirements</span></span>  
 <span data-ttu-id="1d27e-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d27e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d27e-124">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="1d27e-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d27e-125">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1d27e-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d27e-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d27e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d27e-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="1d27e-127">See also</span></span>

- [<span data-ttu-id="1d27e-128">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="1d27e-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1d27e-129">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="1d27e-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
