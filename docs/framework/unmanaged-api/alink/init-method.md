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
ms.openlocfilehash: 606809533010f458272cd6fbbad6234217bddea2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741614"
---
# <a name="init-method"></a><span data-ttu-id="d26be-102">Метод Init</span><span class="sxs-lookup"><span data-stu-id="d26be-102">Init Method</span></span>
<span data-ttu-id="d26be-103">Подготавливает объекты, реализующие [интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) для использования.</span><span class="sxs-lookup"><span data-stu-id="d26be-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d26be-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d26be-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d26be-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d26be-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="d26be-106">[Интерфейс IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) указатель на распределитель метаданных.</span><span class="sxs-lookup"><span data-stu-id="d26be-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="d26be-107">[Интерфейс IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) указатель на интерфейс обработки ошибок, необязательно.</span><span class="sxs-lookup"><span data-stu-id="d26be-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d26be-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d26be-108">Return Value</span></span>  
 <span data-ttu-id="d26be-109">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="d26be-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d26be-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d26be-110">Requirements</span></span>  
 <span data-ttu-id="d26be-111">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="d26be-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d26be-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d26be-112">See also</span></span>

- [<span data-ttu-id="d26be-113">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="d26be-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="d26be-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="d26be-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="d26be-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="d26be-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
