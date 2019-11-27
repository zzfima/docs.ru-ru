---
title: Метод IMetaDataTables::GetBlob
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
ms.openlocfilehash: f5a736d80f36afb8d0a643d4a4e36c9abff01995
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445428"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="ee0c1-102">Метод IMetaDataTables::GetBlob</span><span class="sxs-lookup"><span data-stu-id="ee0c1-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="ee0c1-103">Возвращает указатель на большой двоичный объект (BLOB) по указанному индексу столбца.</span><span class="sxs-lookup"><span data-stu-id="ee0c1-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee0c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee0c1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee0c1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ee0c1-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="ee0c1-106">окне Адрес памяти, из которого необходимо получить `ppData`.</span><span class="sxs-lookup"><span data-stu-id="ee0c1-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="ee0c1-107">заполняет Указатель на размер `ppData`в байтах.</span><span class="sxs-lookup"><span data-stu-id="ee0c1-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="ee0c1-108">заполняет Указатель на указатель на извлекаемые двоичные данные.</span><span class="sxs-lookup"><span data-stu-id="ee0c1-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee0c1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ee0c1-109">Requirements</span></span>  
 <span data-ttu-id="ee0c1-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee0c1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee0c1-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="ee0c1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee0c1-112">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ee0c1-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee0c1-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee0c1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee0c1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ee0c1-114">See also</span></span>

- [<span data-ttu-id="ee0c1-115">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="ee0c1-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="ee0c1-116">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="ee0c1-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
