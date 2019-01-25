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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 315ddf89d9c0653f357490dc31986dc302024622
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662651"
---
# <a name="init-method"></a><span data-ttu-id="9e5df-102">Метод Init</span><span class="sxs-lookup"><span data-stu-id="9e5df-102">Init Method</span></span>
<span data-ttu-id="9e5df-103">Подготавливает объекты, реализующие [интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) для использования.</span><span class="sxs-lookup"><span data-stu-id="9e5df-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e5df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e5df-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e5df-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9e5df-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="9e5df-106">[Интерфейс IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) указатель на распределитель метаданных.</span><span class="sxs-lookup"><span data-stu-id="9e5df-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="9e5df-107">[Интерфейс IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) указатель на интерфейс обработки ошибок, необязательно.</span><span class="sxs-lookup"><span data-stu-id="9e5df-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e5df-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9e5df-108">Return Value</span></span>  
 <span data-ttu-id="9e5df-109">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="9e5df-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e5df-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9e5df-110">Requirements</span></span>  
 <span data-ttu-id="9e5df-111">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="9e5df-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e5df-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9e5df-112">See also</span></span>
- [<span data-ttu-id="9e5df-113">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="9e5df-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="9e5df-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="9e5df-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="9e5df-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="9e5df-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
