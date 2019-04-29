---
title: Метод IMetaDataImport::GetInterfaceImplProps
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76e2ebbd47a5e36a722fce33ba67d7efb4db8675
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777771"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="36b65-102">Метод IMetaDataImport::GetInterfaceImplProps</span><span class="sxs-lookup"><span data-stu-id="36b65-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="36b65-103">Возвращает указатель на токены метаданных для <xref:System.Type> , реализующий заданный метод, и для интерфейса, который объявляет этот метод.</span><span class="sxs-lookup"><span data-stu-id="36b65-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="36b65-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36b65-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36b65-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="36b65-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="36b65-106">[in] Токен метаданных, представляющий метод для возврата маркеров для класса и интерфейса.</span><span class="sxs-lookup"><span data-stu-id="36b65-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="36b65-107">[out] Токен метаданных, представляющий класс, который реализует метод.</span><span class="sxs-lookup"><span data-stu-id="36b65-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="36b65-108">[out] Токен метаданных, представляющий интерфейс, определяющий метод, реализованный.</span><span class="sxs-lookup"><span data-stu-id="36b65-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="36b65-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="36b65-109">Remarks</span></span>

 <span data-ttu-id="36b65-110">Получить значение для `iImpl` путем вызова [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="36b65-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>
 
 <span data-ttu-id="36b65-111">Например, предположим, что класс содержит `mdTypeDef` token значением 0x02000007 и что он реализует три интерфейсы, типы которых имеют токенов:</span><span class="sxs-lookup"><span data-stu-id="36b65-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span> 

- <span data-ttu-id="36b65-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="36b65-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="36b65-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="36b65-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="36b65-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="36b65-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="36b65-115">По существу эта информация хранится в таблицу реализации интерфейса, как:</span><span class="sxs-lookup"><span data-stu-id="36b65-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="36b65-116">Номер строки</span><span class="sxs-lookup"><span data-stu-id="36b65-116">Row number</span></span> | <span data-ttu-id="36b65-117">Маркер класса</span><span class="sxs-lookup"><span data-stu-id="36b65-117">Class token</span></span> | <span data-ttu-id="36b65-118">Токен интерфейса</span><span class="sxs-lookup"><span data-stu-id="36b65-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="36b65-119">4</span><span class="sxs-lookup"><span data-stu-id="36b65-119">4</span></span>          |             |                 |
| <span data-ttu-id="36b65-120">5</span><span class="sxs-lookup"><span data-stu-id="36b65-120">5</span></span>          | <span data-ttu-id="36b65-121">02000007</span><span class="sxs-lookup"><span data-stu-id="36b65-121">02000007</span></span>    | <span data-ttu-id="36b65-122">02000003</span><span class="sxs-lookup"><span data-stu-id="36b65-122">02000003</span></span>        |
| <span data-ttu-id="36b65-123">6</span><span class="sxs-lookup"><span data-stu-id="36b65-123">6</span></span>          | <span data-ttu-id="36b65-124">02000007</span><span class="sxs-lookup"><span data-stu-id="36b65-124">02000007</span></span>    | <span data-ttu-id="36b65-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="36b65-125">0100000A</span></span>        |
| <span data-ttu-id="36b65-126">7</span><span class="sxs-lookup"><span data-stu-id="36b65-126">7</span></span>          |             |                 |
| <span data-ttu-id="36b65-127">8</span><span class="sxs-lookup"><span data-stu-id="36b65-127">8</span></span>          | <span data-ttu-id="36b65-128">02000007</span><span class="sxs-lookup"><span data-stu-id="36b65-128">02000007</span></span>    | <span data-ttu-id="36b65-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="36b65-129">0200001C</span></span>        |

<span data-ttu-id="36b65-130">Помните, что маркер является 4-байтовое значение:</span><span class="sxs-lookup"><span data-stu-id="36b65-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="36b65-131">Нижние 3 байта содержат номер строки, или удалить.</span><span class="sxs-lookup"><span data-stu-id="36b65-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="36b65-132">Старшему байту содержит тип токена — 0x09 для `mdtInterfaceImpl`.</span><span class="sxs-lookup"><span data-stu-id="36b65-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="36b65-133">`GetInterfaceImplProps` Возвращает данные, хранящиеся в строке, маркер которого вами в `iImpl` аргумент.</span><span class="sxs-lookup"><span data-stu-id="36b65-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span> 
  
## <a name="requirements"></a><span data-ttu-id="36b65-134">Требования</span><span class="sxs-lookup"><span data-stu-id="36b65-134">Requirements</span></span>  
 <span data-ttu-id="36b65-135">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36b65-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36b65-136">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="36b65-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36b65-137">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="36b65-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36b65-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36b65-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36b65-139">См. также</span><span class="sxs-lookup"><span data-stu-id="36b65-139">See also</span></span>

- [<span data-ttu-id="36b65-140">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="36b65-140">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="36b65-141">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="36b65-141">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
