---
title: Метод ImportTypes2
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f14822a58f3982d6f9fee1328c10b960657c056f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098472"
---
# <a name="importtypes2-method"></a><span data-ttu-id="eee08-102">Метод ImportTypes2</span><span class="sxs-lookup"><span data-stu-id="eee08-102">ImportTypes2 Method</span></span>
<span data-ttu-id="eee08-103">Инициирует импорт типов.</span><span class="sxs-lookup"><span data-stu-id="eee08-103">Initiates the import of types.</span></span> <span data-ttu-id="eee08-104">Вызовите этот метод, чтобы начать импорт типов из каждой области, импортированной с помощью [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="eee08-104">Call this method to begin importing types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eee08-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eee08-105">Syntax</span></span>  
  
```  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="eee08-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="eee08-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="eee08-107">Идентификатор сборки, в который планируется импортировать.</span><span class="sxs-lookup"><span data-stu-id="eee08-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="eee08-108">Идентификатор файла, из которого импортируются.</span><span class="sxs-lookup"><span data-stu-id="eee08-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="eee08-109">Отсчитываемый от нуля область, из которого импортируются.</span><span class="sxs-lookup"><span data-stu-id="eee08-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="eee08-110">Получает дескриптор перечислителя для типов в заданной области.</span><span class="sxs-lookup"><span data-stu-id="eee08-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="eee08-111">При необходимости получает [интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="eee08-111">Optionally receives [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="eee08-112">При необходимости получает число типов в указанной области.</span><span class="sxs-lookup"><span data-stu-id="eee08-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eee08-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="eee08-113">Return Value</span></span>  
 <span data-ttu-id="eee08-114">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="eee08-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eee08-115">Требования</span><span class="sxs-lookup"><span data-stu-id="eee08-115">Requirements</span></span>  
 <span data-ttu-id="eee08-116">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="eee08-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee08-117">См. также</span><span class="sxs-lookup"><span data-stu-id="eee08-117">See also</span></span>

- [<span data-ttu-id="eee08-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="eee08-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="eee08-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="eee08-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="eee08-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="eee08-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
