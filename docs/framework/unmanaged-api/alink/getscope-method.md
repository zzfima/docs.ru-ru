---
title: Метод GetScope
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b3a0e42e9ffb99896bdd09dbbab65eafb40cafff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777204"
---
# <a name="getscope-method"></a><span data-ttu-id="e3182-102">Метод GetScope</span><span class="sxs-lookup"><span data-stu-id="e3182-102">GetScope Method</span></span>
<span data-ttu-id="e3182-103">Возвращает область импорта.</span><span class="sxs-lookup"><span data-stu-id="e3182-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3182-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3182-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3182-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e3182-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e3182-106">Уникальный идентификатор сборки для импорта.</span><span class="sxs-lookup"><span data-stu-id="e3182-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="e3182-107">Уникальный идентификатор файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="e3182-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="e3182-108">Отсчитываемая от нуля область для импорта.</span><span class="sxs-lookup"><span data-stu-id="e3182-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="e3182-109">Получает интерфейс [интерфейса IMetaDataImport](../metadata/imetadataimport-interface.md) для области.</span><span class="sxs-lookup"><span data-stu-id="e3182-109">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3182-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e3182-110">Return Value</span></span>  
 <span data-ttu-id="e3182-111">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="e3182-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3182-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e3182-112">Requirements</span></span>  
 <span data-ttu-id="e3182-113">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="e3182-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3182-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e3182-114">See also</span></span>

- [<span data-ttu-id="e3182-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="e3182-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e3182-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="e3182-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e3182-117">API ALink</span><span class="sxs-lookup"><span data-stu-id="e3182-117">ALink API</span></span>](index.md)
