---
title: Метод IMetaDataEmit::SetFieldRVA
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type:
- apiref
ms.openlocfilehash: 501199bedec3b7a65d95c80cdef178831a65fd01
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428414"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="ca5d7-102">Метод IMetaDataEmit::SetFieldRVA</span><span class="sxs-lookup"><span data-stu-id="ca5d7-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="ca5d7-103">Задает значение глобальной переменной для относительного виртуального адреса поля, на которое ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca5d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca5d7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca5d7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca5d7-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="ca5d7-106">окне Токен для целевого поля.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="ca5d7-107">окне Адрес кода или области данных.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca5d7-108">Требования</span><span class="sxs-lookup"><span data-stu-id="ca5d7-108">Requirements</span></span>  
 <span data-ttu-id="ca5d7-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca5d7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca5d7-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="ca5d7-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ca5d7-111">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ca5d7-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca5d7-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca5d7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca5d7-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="ca5d7-113">See also</span></span>

- [<span data-ttu-id="ca5d7-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="ca5d7-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ca5d7-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="ca5d7-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
