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
ms.openlocfilehash: 60602462376543fe934bb3c58bc4988fa8ab34bf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119370"
---
# <a name="init-method"></a><span data-ttu-id="e0523-102">Метод Init</span><span class="sxs-lookup"><span data-stu-id="e0523-102">Init Method</span></span>
<span data-ttu-id="e0523-103">Подготавливает объекты, реализующие [интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) для использования.</span><span class="sxs-lookup"><span data-stu-id="e0523-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0523-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0523-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0523-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0523-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="e0523-106">[Интерфейс IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) указатель на распределитель метаданных.</span><span class="sxs-lookup"><span data-stu-id="e0523-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="e0523-107">[Интерфейс IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) указатель на интерфейс обработки ошибок, необязательно.</span><span class="sxs-lookup"><span data-stu-id="e0523-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0523-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e0523-108">Return Value</span></span>  
 <span data-ttu-id="e0523-109">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="e0523-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0523-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e0523-110">Requirements</span></span>  
 <span data-ttu-id="e0523-111">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="e0523-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0523-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e0523-112">See also</span></span>

- [<span data-ttu-id="e0523-113">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="e0523-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="e0523-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="e0523-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="e0523-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="e0523-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
