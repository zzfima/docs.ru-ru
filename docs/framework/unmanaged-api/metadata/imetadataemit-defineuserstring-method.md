---
title: Метод IMetaDataEmit::DefineUserString
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f24dd3864be1bda454ac5e863f3fa2caf736bda9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050120"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="da512-102">Метод IMetaDataEmit::DefineUserString</span><span class="sxs-lookup"><span data-stu-id="da512-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="da512-103">Получает маркер метаданных для заданной строки литерала.</span><span class="sxs-lookup"><span data-stu-id="da512-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da512-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da512-104">Syntax</span></span>  
  
```  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da512-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="da512-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="da512-106">[in] Строка пользователя для хранения.</span><span class="sxs-lookup"><span data-stu-id="da512-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="da512-107">[in] Число расширенных символов в `szString`.</span><span class="sxs-lookup"><span data-stu-id="da512-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="da512-108">[out] Маркер строки, назначенный.</span><span class="sxs-lookup"><span data-stu-id="da512-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da512-109">Требования</span><span class="sxs-lookup"><span data-stu-id="da512-109">Requirements</span></span>  
 <span data-ttu-id="da512-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da512-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da512-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="da512-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da512-112">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da512-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da512-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da512-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da512-114">См. также</span><span class="sxs-lookup"><span data-stu-id="da512-114">See also</span></span>

- [<span data-ttu-id="da512-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="da512-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="da512-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="da512-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
