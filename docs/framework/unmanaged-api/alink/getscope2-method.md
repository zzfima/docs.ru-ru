---
title: Метод GetScope2
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
ms.openlocfilehash: a5b080443be94d5a298cc67591914d87470e6f48
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447188"
---
# <a name="getscope2-method"></a><span data-ttu-id="61fd7-102">Метод GetScope2</span><span class="sxs-lookup"><span data-stu-id="61fd7-102">GetScope2 Method</span></span>
<span data-ttu-id="61fd7-103">Возвращает область импорта.</span><span class="sxs-lookup"><span data-stu-id="61fd7-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61fd7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61fd7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="61fd7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="61fd7-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="61fd7-106">Идентификатор целевой сборки.</span><span class="sxs-lookup"><span data-stu-id="61fd7-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="61fd7-107">Идентификатор файла, из которого необходимо выполнить импорт.</span><span class="sxs-lookup"><span data-stu-id="61fd7-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="61fd7-108">Отсчитываемая от нуля область для импорта.</span><span class="sxs-lookup"><span data-stu-id="61fd7-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="61fd7-109">Получает указатель на интерфейс интерфейса [IMetaDataImport2](../metadata/imetadataimport2-interface.md) для указанной области.</span><span class="sxs-lookup"><span data-stu-id="61fd7-109">Receives pointer to [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61fd7-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="61fd7-110">Return Value</span></span>  
 <span data-ttu-id="61fd7-111">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="61fd7-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61fd7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="61fd7-112">Requirements</span></span>  
 <span data-ttu-id="61fd7-113">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="61fd7-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61fd7-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="61fd7-114">See also</span></span>

- [<span data-ttu-id="61fd7-115">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="61fd7-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="61fd7-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="61fd7-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="61fd7-117">API ALink</span><span class="sxs-lookup"><span data-stu-id="61fd7-117">ALink API</span></span>](index.md)
