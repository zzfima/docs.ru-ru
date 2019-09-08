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
ms.openlocfilehash: ce09eca30e1edb9e1afc02216a07955a5fed4fd2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787254"
---
# <a name="importtypes2-method"></a><span data-ttu-id="51dbb-102">Метод ImportTypes2</span><span class="sxs-lookup"><span data-stu-id="51dbb-102">ImportTypes2 Method</span></span>
<span data-ttu-id="51dbb-103">Инициирует импорт типов.</span><span class="sxs-lookup"><span data-stu-id="51dbb-103">Initiates the import of types.</span></span> <span data-ttu-id="51dbb-104">Вызовите этот метод, чтобы начать импорт типов из каждой области, импортированной с помощью [метода ImportFile](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="51dbb-104">Call this method to begin importing types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51dbb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51dbb-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="51dbb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="51dbb-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="51dbb-107">Идентификатор сборки, в которую необходимо выполнить импорт.</span><span class="sxs-lookup"><span data-stu-id="51dbb-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="51dbb-108">Идентификатор файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="51dbb-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="51dbb-109">Отсчитываемая от нуля область, из которой производится импорт.</span><span class="sxs-lookup"><span data-stu-id="51dbb-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="51dbb-110">Получает обработчик перечислителя для типов в заданной области.</span><span class="sxs-lookup"><span data-stu-id="51dbb-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="51dbb-111">При необходимости получает интерфейс интерфейса [IMetaDataImport2](../metadata/imetadataimport2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="51dbb-111">Optionally receives [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="51dbb-112">При необходимости получает число типов в указанной области.</span><span class="sxs-lookup"><span data-stu-id="51dbb-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51dbb-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="51dbb-113">Return Value</span></span>  
 <span data-ttu-id="51dbb-114">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="51dbb-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51dbb-115">Требования</span><span class="sxs-lookup"><span data-stu-id="51dbb-115">Requirements</span></span>  
 <span data-ttu-id="51dbb-116">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="51dbb-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51dbb-117">См. также</span><span class="sxs-lookup"><span data-stu-id="51dbb-117">See also</span></span>

- [<span data-ttu-id="51dbb-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="51dbb-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="51dbb-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="51dbb-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="51dbb-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="51dbb-120">ALink API</span></span>](index.md)
