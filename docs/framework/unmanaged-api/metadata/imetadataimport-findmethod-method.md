---
title: Метод IMetaDataImport::FindMethod
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4c0f25b50bf2948bb6f096db70fff208cef799bc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587311"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="4fc2f-102">Метод IMetaDataImport::FindMethod</span><span class="sxs-lookup"><span data-stu-id="4fc2f-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="4fc2f-103">Возвращает указатель на MethodDef токен для метода, который заключен заданным <xref:System.Type> , с указанной сигнатурой имени и метаданных.</span><span class="sxs-lookup"><span data-stu-id="4fc2f-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fc2f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4fc2f-104">Syntax</span></span>  
  
```  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4fc2f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4fc2f-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="4fc2f-106">[in] `mdTypeDef` Маркер типа (класса или интерфейса), ограничивающий элемент для поиска.</span><span class="sxs-lookup"><span data-stu-id="4fc2f-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="4fc2f-107">Если это значение равно `mdTokenNil`, а затем поиск выполняется для глобальной функции.</span><span class="sxs-lookup"><span data-stu-id="4fc2f-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="4fc2f-108">[in] Имя метода для поиска.</span><span class="sxs-lookup"><span data-stu-id="4fc2f-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="4fc2f-109">[in] Указатель на двоичную подпись метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="4fc2f-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="4fc2f-110">[in] Размер в байтах `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="4fc2f-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="4fc2f-111">[out] Указатель на соответствующий токен MethodDef.</span><span class="sxs-lookup"><span data-stu-id="4fc2f-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fc2f-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="4fc2f-112">Remarks</span></span>  
 <span data-ttu-id="4fc2f-113">Укажите метод, с помощью его во включающий класс или интерфейс (`td`), его имя (`szName`) и при необходимости его подпись (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="4fc2f-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="4fc2f-114">Может существовать несколько методов с одинаковыми именами в классе или интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="4fc2f-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="4fc2f-115">В этом случае следует передайте сигнатуры метода, чтобы найти уникальное соответствие.</span><span class="sxs-lookup"><span data-stu-id="4fc2f-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="4fc2f-116">Подпись передается `FindMethod` необходимо создавать в текущей области, поскольку подписи привязаны к определенной области.</span><span class="sxs-lookup"><span data-stu-id="4fc2f-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="4fc2f-117">Подписи можно внедрить токен, который определяет включающего класса или типа значения.</span><span class="sxs-lookup"><span data-stu-id="4fc2f-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="4fc2f-118">Маркер — это индекс в локальной таблице TypeDef.</span><span class="sxs-lookup"><span data-stu-id="4fc2f-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="4fc2f-119">Не удается построить выполнения вне контекста текущей области и использовать ее как входных данных, вводимых в `FindMethod`.</span><span class="sxs-lookup"><span data-stu-id="4fc2f-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="4fc2f-120">`FindMethod` находит только те методы, которые были определены непосредственно в классе или интерфейсе; унаследованные методы не найден.</span><span class="sxs-lookup"><span data-stu-id="4fc2f-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fc2f-121">Требования</span><span class="sxs-lookup"><span data-stu-id="4fc2f-121">Requirements</span></span>  
 <span data-ttu-id="4fc2f-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fc2f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fc2f-123">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4fc2f-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4fc2f-124">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4fc2f-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4fc2f-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fc2f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc2f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4fc2f-126">See also</span></span>
- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="4fc2f-127">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4fc2f-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4fc2f-128">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4fc2f-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
