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
ms.openlocfilehash: bf96770dd58c9b84596c082a615f626ec723cc6c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787250"
---
# <a name="init-method"></a><span data-ttu-id="22f7a-102">Метод Init</span><span class="sxs-lookup"><span data-stu-id="22f7a-102">Init Method</span></span>
<span data-ttu-id="22f7a-103">Подготавливает объекты, реализующие [интерфейс иалинк](ialink-interface.md) для использования.</span><span class="sxs-lookup"><span data-stu-id="22f7a-103">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22f7a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22f7a-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="22f7a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="22f7a-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="22f7a-106">Указатель [интерфейса IMetaDataDispenserEx](../metadata/imetadatadispenserex-interface.md) на распределитель метаданных.</span><span class="sxs-lookup"><span data-stu-id="22f7a-106">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="22f7a-107">Указатель [интерфейса IMetaDataError](../metadata/imetadataerror-interface.md) на необязательный интерфейс обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="22f7a-107">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22f7a-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="22f7a-108">Return Value</span></span>  
 <span data-ttu-id="22f7a-109">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="22f7a-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22f7a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="22f7a-110">Requirements</span></span>  
 <span data-ttu-id="22f7a-111">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="22f7a-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22f7a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="22f7a-112">See also</span></span>

- [<span data-ttu-id="22f7a-113">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="22f7a-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="22f7a-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="22f7a-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="22f7a-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="22f7a-115">ALink API</span></span>](index.md)
