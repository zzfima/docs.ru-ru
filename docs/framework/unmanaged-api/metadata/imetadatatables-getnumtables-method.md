---
title: Метод IMetaDataTables::GetNumTables
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNumTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNumTables
helpviewer_keywords:
- GetNumTables method [.NET Framework metadata]
- IMetaDataTables::GetNumTables method [.NET Framework metadata]
ms.assetid: 8196f2a3-bbf2-45d3-a6cd-74502c356644
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2dc7d8c339e5f77bad44960092198035e13735b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54621296"
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="44d40-102">Метод IMetaDataTables::GetNumTables</span><span class="sxs-lookup"><span data-stu-id="44d40-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="44d40-103">Получает количество таблиц в области текущего `IMetaDataTables` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="44d40-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44d40-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44d40-104">Syntax</span></span>  
  
```  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44d40-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="44d40-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="44d40-106">[out] Указатель на количество таблиц в области текущего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="44d40-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44d40-107">Требования</span><span class="sxs-lookup"><span data-stu-id="44d40-107">Requirements</span></span>  
 <span data-ttu-id="44d40-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44d40-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44d40-109">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="44d40-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44d40-110">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="44d40-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="44d40-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44d40-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44d40-112">См. также</span><span class="sxs-lookup"><span data-stu-id="44d40-112">See also</span></span>
- [<span data-ttu-id="44d40-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="44d40-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="44d40-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="44d40-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
