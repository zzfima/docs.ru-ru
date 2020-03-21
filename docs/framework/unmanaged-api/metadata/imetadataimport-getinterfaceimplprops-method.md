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
ms.openlocfilehash: 4b8ddf7fec12d175f030c0ea0ed982c6fb334aee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175386"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="aa8b6-102">Метод IMetaDataImport::GetInterfaceImplProps</span><span class="sxs-lookup"><span data-stu-id="aa8b6-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="aa8b6-103">Получает указатель на маркеры метаданных <xref:System.Type> для того, который реализует указанный метод, и для интерфейса, который декларирует этот метод.</span><span class="sxs-lookup"><span data-stu-id="aa8b6-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="aa8b6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa8b6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa8b6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aa8b6-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="aa8b6-106">(в) Токен метаданных, представляющий метод возврата маркеров класса и интерфейса.</span><span class="sxs-lookup"><span data-stu-id="aa8b6-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="aa8b6-107">(ваут) Токен метаданных, представляющий класс, реализующий метод.</span><span class="sxs-lookup"><span data-stu-id="aa8b6-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="aa8b6-108">(ваут) Токен метаданных, представляющий интерфейс, определяющий реализованный метод.</span><span class="sxs-lookup"><span data-stu-id="aa8b6-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="aa8b6-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="aa8b6-109">Remarks</span></span>

 <span data-ttu-id="aa8b6-110">Значение для `iImpl` получения, позвонив в метод [EnumInterfaceImpls.](imetadataimport-enuminterfaceimpls-method.md)</span><span class="sxs-lookup"><span data-stu-id="aa8b6-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>

 <span data-ttu-id="aa8b6-111">Например, предположим, что `mdTypeDef` класс имеет значение маркера 0x02000007 и что он реализует три интерфейса, типы которых имеют токены:</span><span class="sxs-lookup"><span data-stu-id="aa8b6-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span>

- <span data-ttu-id="aa8b6-112">0x0200003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="aa8b6-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="aa8b6-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="aa8b6-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="aa8b6-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="aa8b6-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="aa8b6-115">Концептуально эта информация хранится в таблице реализации интерфейса как:</span><span class="sxs-lookup"><span data-stu-id="aa8b6-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="aa8b6-116">Номер строки</span><span class="sxs-lookup"><span data-stu-id="aa8b6-116">Row number</span></span> | <span data-ttu-id="aa8b6-117">Токен класса</span><span class="sxs-lookup"><span data-stu-id="aa8b6-117">Class token</span></span> | <span data-ttu-id="aa8b6-118">Токен интерфейса</span><span class="sxs-lookup"><span data-stu-id="aa8b6-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="aa8b6-119">4</span><span class="sxs-lookup"><span data-stu-id="aa8b6-119">4</span></span>          |             |                 |
| <span data-ttu-id="aa8b6-120">5</span><span class="sxs-lookup"><span data-stu-id="aa8b6-120">5</span></span>          | <span data-ttu-id="aa8b6-121">02000007</span><span class="sxs-lookup"><span data-stu-id="aa8b6-121">02000007</span></span>    | <span data-ttu-id="aa8b6-122">02000003</span><span class="sxs-lookup"><span data-stu-id="aa8b6-122">02000003</span></span>        |
| <span data-ttu-id="aa8b6-123">6</span><span class="sxs-lookup"><span data-stu-id="aa8b6-123">6</span></span>          | <span data-ttu-id="aa8b6-124">02000007</span><span class="sxs-lookup"><span data-stu-id="aa8b6-124">02000007</span></span>    | <span data-ttu-id="aa8b6-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="aa8b6-125">0100000A</span></span>        |
| <span data-ttu-id="aa8b6-126">7</span><span class="sxs-lookup"><span data-stu-id="aa8b6-126">7</span></span>          |             |                 |
| <span data-ttu-id="aa8b6-127">8</span><span class="sxs-lookup"><span data-stu-id="aa8b6-127">8</span></span>          | <span data-ttu-id="aa8b6-128">02000007</span><span class="sxs-lookup"><span data-stu-id="aa8b6-128">02000007</span></span>    | <span data-ttu-id="aa8b6-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="aa8b6-129">0200001C</span></span>        |

<span data-ttu-id="aa8b6-130">Напомним, токен представляет собой значение 4 байт:</span><span class="sxs-lookup"><span data-stu-id="aa8b6-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="aa8b6-131">Нижние 3 байта удерживают рядное число, или RID.</span><span class="sxs-lookup"><span data-stu-id="aa8b6-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="aa8b6-132">Верхний байт содержит тип маркера - `mdtInterfaceImpl`0x09 для .</span><span class="sxs-lookup"><span data-stu-id="aa8b6-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="aa8b6-133">`GetInterfaceImplProps`возвращает информацию, хранявшуюся в `iImpl` строке, токен которой вы предоставляете в споре.</span><span class="sxs-lookup"><span data-stu-id="aa8b6-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="aa8b6-134">Требования</span><span class="sxs-lookup"><span data-stu-id="aa8b6-134">Requirements</span></span>  
 <span data-ttu-id="aa8b6-135">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa8b6-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa8b6-136">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aa8b6-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa8b6-137">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aa8b6-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aa8b6-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa8b6-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa8b6-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aa8b6-139">See also</span></span>

- [<span data-ttu-id="aa8b6-140">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="aa8b6-140">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="aa8b6-141">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="aa8b6-141">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
