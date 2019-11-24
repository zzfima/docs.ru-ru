---
title: Метод Init
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
ms.openlocfilehash: 986ae69e7ebb8f607be5d37fab426bcc787abb26
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445638"
---
# <a name="init-method"></a><span data-ttu-id="bcc60-102">Метод Init</span><span class="sxs-lookup"><span data-stu-id="bcc60-102">Init Method</span></span>
<span data-ttu-id="bcc60-103">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span><span class="sxs-lookup"><span data-stu-id="bcc60-103">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcc60-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bcc60-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcc60-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bcc60-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="bcc60-106">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span><span class="sxs-lookup"><span data-stu-id="bcc60-106">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="bcc60-107">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span><span class="sxs-lookup"><span data-stu-id="bcc60-107">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bcc60-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bcc60-108">Return Value</span></span>  
 <span data-ttu-id="bcc60-109">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="bcc60-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcc60-110">Требования</span><span class="sxs-lookup"><span data-stu-id="bcc60-110">Requirements</span></span>  
 <span data-ttu-id="bcc60-111">Requires alink.h</span><span class="sxs-lookup"><span data-stu-id="bcc60-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcc60-112">См. также</span><span class="sxs-lookup"><span data-stu-id="bcc60-112">See also</span></span>

- [<span data-ttu-id="bcc60-113">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="bcc60-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="bcc60-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="bcc60-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="bcc60-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="bcc60-115">ALink API</span></span>](index.md)
