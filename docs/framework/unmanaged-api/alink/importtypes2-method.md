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
ms.openlocfilehash: 51c696679626a598be422376e9dc89b5add1773d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400495"
---
# <a name="importtypes2-method"></a><span data-ttu-id="dc777-102">Метод ImportTypes2</span><span class="sxs-lookup"><span data-stu-id="dc777-102">ImportTypes2 Method</span></span>
<span data-ttu-id="dc777-103">Инициирует импорт типов.</span><span class="sxs-lookup"><span data-stu-id="dc777-103">Initiates the import of types.</span></span> <span data-ttu-id="dc777-104">Вызовите этот метод, чтобы начать импорт типов из каждой области, импортированной посредством [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="dc777-104">Call this method to begin importing types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc777-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc777-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="dc777-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="dc777-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="dc777-107">Идентификатор сборки, в который планируется импортировать.</span><span class="sxs-lookup"><span data-stu-id="dc777-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="dc777-108">Идентификатор файла, из которого требуется импортировать.</span><span class="sxs-lookup"><span data-stu-id="dc777-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="dc777-109">Отсчитываемый от нуля область, из которого требуется импортировать.</span><span class="sxs-lookup"><span data-stu-id="dc777-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="dc777-110">Получает дескриптор перечислителя для типов в заданной области.</span><span class="sxs-lookup"><span data-stu-id="dc777-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="dc777-111">При необходимости получает [IMetaDataImport2-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="dc777-111">Optionally receives [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="dc777-112">При необходимости получает число типов в указанной области.</span><span class="sxs-lookup"><span data-stu-id="dc777-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc777-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dc777-113">Return Value</span></span>  
 <span data-ttu-id="dc777-114">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="dc777-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc777-115">Требования</span><span class="sxs-lookup"><span data-stu-id="dc777-115">Requirements</span></span>  
 <span data-ttu-id="dc777-116">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="dc777-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc777-117">См. также</span><span class="sxs-lookup"><span data-stu-id="dc777-117">See Also</span></span>  
 [<span data-ttu-id="dc777-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="dc777-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="dc777-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="dc777-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="dc777-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="dc777-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
