---
title: Метод IMetaDataImport::FindField
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b07d75b6a8839f9a223ef2c0be52830e107e4088
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527605"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="22d0b-102">Метод IMetaDataImport::FindField</span><span class="sxs-lookup"><span data-stu-id="22d0b-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="22d0b-103">Возвращает указатель на FieldDef токен для поля, которое заключено заданным <xref:System.Type> , с указанной сигнатурой имени и метаданных.</span><span class="sxs-lookup"><span data-stu-id="22d0b-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22d0b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22d0b-104">Syntax</span></span>  
  
```  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22d0b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="22d0b-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="22d0b-106">[in] Токен TypeDef для класса или интерфейса, который содержит поле для поиска.</span><span class="sxs-lookup"><span data-stu-id="22d0b-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="22d0b-107">Если это значение равно `mdTokenNil`, поиск выполняется для глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="22d0b-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="22d0b-108">[in] Имя поля для поиска.</span><span class="sxs-lookup"><span data-stu-id="22d0b-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="22d0b-109">[in] Указатель на двоичную подпись метаданных поля.</span><span class="sxs-lookup"><span data-stu-id="22d0b-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="22d0b-110">[in] Размер в байтах `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="22d0b-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="22d0b-111">[out] Указатель на соответствующий токен FieldDef.</span><span class="sxs-lookup"><span data-stu-id="22d0b-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22d0b-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="22d0b-112">Remarks</span></span>  
 <span data-ttu-id="22d0b-113">Укажите поле, используя его во включающий класс или интерфейс (`td`), его имя (`szName`) и при необходимости его подпись (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="22d0b-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="22d0b-114">Подпись передается `FindField` необходимо создавать в текущей области, поскольку подписи привязаны к определенной области.</span><span class="sxs-lookup"><span data-stu-id="22d0b-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="22d0b-115">Подписи можно внедрить токен, который определяет включающего класса или типа значения.</span><span class="sxs-lookup"><span data-stu-id="22d0b-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="22d0b-116">(Маркер — это индекс в локальной таблице TypeDef).</span><span class="sxs-lookup"><span data-stu-id="22d0b-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="22d0b-117">Не удается построить выполнения вне контекста текущей области и использовать ее в качестве входных данных для `FindField`.</span><span class="sxs-lookup"><span data-stu-id="22d0b-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="22d0b-118">`FindField` находит только те поля, которые были определены непосредственно в классе или интерфейсе; не удается найти унаследованные поля.</span><span class="sxs-lookup"><span data-stu-id="22d0b-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22d0b-119">Требования</span><span class="sxs-lookup"><span data-stu-id="22d0b-119">Requirements</span></span>  
 <span data-ttu-id="22d0b-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22d0b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22d0b-121">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="22d0b-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="22d0b-122">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="22d0b-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="22d0b-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22d0b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22d0b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="22d0b-124">See also</span></span>
- [<span data-ttu-id="22d0b-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="22d0b-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="22d0b-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="22d0b-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
