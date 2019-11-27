---
title: Метод IMetaDataImport::FindMember
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
ms.openlocfilehash: 7a46fa5319a1badc0cf28dcdbf535a6ed017c9c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437918"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="d103e-102">Метод IMetaDataImport::FindMember</span><span class="sxs-lookup"><span data-stu-id="d103e-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="d103e-103">Возвращает указатель на токен Мембердеф для поля или метода, заключенного в заданное <xref:System.Type> и имеющего указанное имя и подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="d103e-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d103e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d103e-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d103e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d103e-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="d103e-106">окне Токен TypeDef для класса или интерфейса, который заключает элемент для поиска.</span><span class="sxs-lookup"><span data-stu-id="d103e-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="d103e-107">Если это значение равно `mdTokenNil`, поиск выполняется для глобальной переменной или глобальной функции.</span><span class="sxs-lookup"><span data-stu-id="d103e-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="d103e-108">окне Имя искомого элемента.</span><span class="sxs-lookup"><span data-stu-id="d103e-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="d103e-109">окне Указатель на сигнатуру двоичных метаданных элемента.</span><span class="sxs-lookup"><span data-stu-id="d103e-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="d103e-110">окне Размер в байтах `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="d103e-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="d103e-111">заполняет Указатель на соответствующий токен Мембердеф.</span><span class="sxs-lookup"><span data-stu-id="d103e-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d103e-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="d103e-112">Remarks</span></span>  
 <span data-ttu-id="d103e-113">Элемент указывается с помощью включающего класса или интерфейса (`td`), его имени (`szName`) и, при необходимости, его сигнатуры (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="d103e-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="d103e-114">В классе или интерфейсе может быть несколько членов с одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="d103e-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="d103e-115">В этом случае передайте сигнатуру члена, чтобы найти уникальное совпадение.</span><span class="sxs-lookup"><span data-stu-id="d103e-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="d103e-116">Подпись, передаваемая `FindMember`, должна быть создана в текущей области, так как сигнатуры привязаны к определенной области.</span><span class="sxs-lookup"><span data-stu-id="d103e-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="d103e-117">Сигнатура может внедрять маркер, идентифицирующий включающий класс или тип значения.</span><span class="sxs-lookup"><span data-stu-id="d103e-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="d103e-118">Токен является индексом локальной таблицы TypeDef.</span><span class="sxs-lookup"><span data-stu-id="d103e-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="d103e-119">Нельзя построить подпись времени выполнения вне контекста текущей области и использовать эту сигнатуру в качестве входных данных для `FindMember`.</span><span class="sxs-lookup"><span data-stu-id="d103e-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="d103e-120">`FindMember` находит только элементы, которые были определены непосредственно в классе или интерфейсе; Он не находит наследуемых членов.</span><span class="sxs-lookup"><span data-stu-id="d103e-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d103e-121">`FindMember` является вспомогательным методом.</span><span class="sxs-lookup"><span data-stu-id="d103e-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="d103e-122">Он вызывает метод [IMetaDataImport:: FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); Если этот вызов не находит совпадения, `FindMember` вызывает метод [IMetaDataImport:: финдфиелд](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span><span class="sxs-lookup"><span data-stu-id="d103e-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d103e-123">Требования</span><span class="sxs-lookup"><span data-stu-id="d103e-123">Requirements</span></span>  
 <span data-ttu-id="d103e-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d103e-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d103e-125">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="d103e-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d103e-126">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d103e-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d103e-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d103e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d103e-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d103e-128">See also</span></span>

- [<span data-ttu-id="d103e-129">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d103e-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d103e-130">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d103e-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
