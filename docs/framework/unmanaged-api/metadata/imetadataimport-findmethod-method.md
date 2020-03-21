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
ms.openlocfilehash: 53b3d94e8b1e273fcbc041d25a5bf586a12735c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177250"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="f9628-102">Метод IMetaDataImport::FindMethod</span><span class="sxs-lookup"><span data-stu-id="f9628-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="f9628-103">Получает указатель на токен MethodDef для метода, который <xref:System.Type> прилагается указанным и который имеет указанное имя и подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="f9628-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9628-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9628-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9628-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f9628-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="f9628-106">(в) Токен `mdTypeDef` для типа (класс или интерфейс), который примыкает к поиску участника.</span><span class="sxs-lookup"><span data-stu-id="f9628-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="f9628-107">Если это `mdTokenNil`значение, то поиск делается для глобальной функции.</span><span class="sxs-lookup"><span data-stu-id="f9628-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="f9628-108">(в) Название метода поиска.</span><span class="sxs-lookup"><span data-stu-id="f9628-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="f9628-109">(в) Указатель на двоичную подпись метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="f9628-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="f9628-110">(в) Размер байтов `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="f9628-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="f9628-111">(ваут) Указатель на соответствующий токен MethodDef.</span><span class="sxs-lookup"><span data-stu-id="f9628-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9628-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="f9628-112">Remarks</span></span>  
 <span data-ttu-id="f9628-113">Вы указываете метод, используя его`td`прилагающий`szName`класс или интерфейс (`pvSigBlob`), его имя ( ), и дополнительно его подпись ( ).</span><span class="sxs-lookup"><span data-stu-id="f9628-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="f9628-114">В классе или интерфейсе может быть несколько методов с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="f9628-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="f9628-115">В этом случае, пройти подпись метода, чтобы найти уникальный матч.</span><span class="sxs-lookup"><span data-stu-id="f9628-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="f9628-116">Подпись, `FindMethod` переданная, должна быть сгенерирована в текущей области, поскольку подписи привязаны к определенной области.</span><span class="sxs-lookup"><span data-stu-id="f9628-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="f9628-117">Подпись может вставлять маркер, который определяет класс или тип значения.</span><span class="sxs-lookup"><span data-stu-id="f9628-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="f9628-118">Токен — это индекс в локальной таблице TypeDef.</span><span class="sxs-lookup"><span data-stu-id="f9628-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="f9628-119">Нельзя создавать подпись времени выполнения вне контекста текущей области и использовать `FindMethod`эту подпись в качестве ввода для ввода.</span><span class="sxs-lookup"><span data-stu-id="f9628-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="f9628-120">`FindMethod`находит только методы, которые были определены непосредственно в классе или интерфейсе; он не находит унаследованных методов.</span><span class="sxs-lookup"><span data-stu-id="f9628-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9628-121">Требования</span><span class="sxs-lookup"><span data-stu-id="f9628-121">Requirements</span></span>  
 <span data-ttu-id="f9628-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9628-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9628-123">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f9628-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f9628-124">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f9628-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f9628-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9628-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9628-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f9628-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="f9628-127">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f9628-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f9628-128">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f9628-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
