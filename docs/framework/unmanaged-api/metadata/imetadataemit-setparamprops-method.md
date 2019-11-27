---
title: Метод IMetaDataEmit::SetParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
ms.openlocfilehash: 813460aa027b259866b168d426fd28502b5c4465
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432493"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="44e63-102">Метод IMetaDataEmit::SetParamProps</span><span class="sxs-lookup"><span data-stu-id="44e63-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="44e63-103">Задает или изменяет функции параметра метода, который был определен при предыдущем вызове [IMetaDataEmit::D ефинепарам](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="44e63-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44e63-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44e63-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParamProps (   
    [in]  mdParamDef  pd,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44e63-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="44e63-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="44e63-106">окне Токен для целевого параметра.</span><span class="sxs-lookup"><span data-stu-id="44e63-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="44e63-107">окне Имя параметра в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="44e63-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="44e63-108">окне Флаги для параметра.</span><span class="sxs-lookup"><span data-stu-id="44e63-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="44e63-109">окне ELEMENT_TYPE_ \* для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="44e63-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="44e63-110">окне Постоянное значение для параметра.</span><span class="sxs-lookup"><span data-stu-id="44e63-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="44e63-111">окне Размер (в Юникоде) символов `pValue`.</span><span class="sxs-lookup"><span data-stu-id="44e63-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44e63-112">Требования</span><span class="sxs-lookup"><span data-stu-id="44e63-112">Requirements</span></span>  
 <span data-ttu-id="44e63-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44e63-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44e63-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="44e63-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44e63-115">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="44e63-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44e63-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44e63-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e63-117">См. также</span><span class="sxs-lookup"><span data-stu-id="44e63-117">See also</span></span>

- [<span data-ttu-id="44e63-118">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="44e63-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="44e63-119">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="44e63-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
