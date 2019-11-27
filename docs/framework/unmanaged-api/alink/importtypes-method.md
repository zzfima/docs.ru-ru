---
title: Метод ImportTypes
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
ms.openlocfilehash: 76d2b163f959111923bffb1348890f6fbb29828e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445677"
---
# <a name="importtypes-method"></a><span data-ttu-id="bf7d6-102">Метод ImportTypes</span><span class="sxs-lookup"><span data-stu-id="bf7d6-102">ImportTypes Method</span></span>
<span data-ttu-id="bf7d6-103">Инициирует импорт типов из каждой области, импортированной с помощью [метода ImportFile](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="bf7d6-103">Initiates the importing of types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf7d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf7d6-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf7d6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf7d6-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="bf7d6-106">Идентификатор сборки, в которую необходимо выполнить импорт.</span><span class="sxs-lookup"><span data-stu-id="bf7d6-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="bf7d6-107">Идентификатор файла, из которого необходимо выполнить импорт.</span><span class="sxs-lookup"><span data-stu-id="bf7d6-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="bf7d6-108">Отсчитываемая от нуля область для импорта.</span><span class="sxs-lookup"><span data-stu-id="bf7d6-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="bf7d6-109">Получает обработчики перечислителя для типов в этой области.</span><span class="sxs-lookup"><span data-stu-id="bf7d6-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="bf7d6-110">При необходимости получает интерфейс [интерфейса IMetaDataImport](../metadata/imetadataimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="bf7d6-110">Optionally receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="bf7d6-111">При необходимости получает число типов в указанной области.</span><span class="sxs-lookup"><span data-stu-id="bf7d6-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf7d6-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bf7d6-112">Return Value</span></span>  
 <span data-ttu-id="bf7d6-113">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="bf7d6-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf7d6-114">Требования</span><span class="sxs-lookup"><span data-stu-id="bf7d6-114">Requirements</span></span>  
 <span data-ttu-id="bf7d6-115">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="bf7d6-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf7d6-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="bf7d6-116">See also</span></span>

- [<span data-ttu-id="bf7d6-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="bf7d6-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="bf7d6-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="bf7d6-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="bf7d6-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="bf7d6-119">ALink API</span></span>](index.md)
