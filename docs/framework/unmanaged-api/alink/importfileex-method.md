---
title: Метод ImportFileEx
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd138d0418bb9667a86419d719bf0b95a4bb1b12
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777116"
---
# <a name="importfileex-method"></a><span data-ttu-id="5673f-102">Метод ImportFileEx</span><span class="sxs-lookup"><span data-stu-id="5673f-102">ImportFileEx Method</span></span>
<span data-ttu-id="5673f-103">Импортирует указанную сборку или непривязанный модуль.</span><span class="sxs-lookup"><span data-stu-id="5673f-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5673f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5673f-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5673f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5673f-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="5673f-106">Полное имя файла, из которого необходимо выполнить импорт.</span><span class="sxs-lookup"><span data-stu-id="5673f-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="5673f-107">Необязательное имя целевого файла.</span><span class="sxs-lookup"><span data-stu-id="5673f-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="5673f-108">Если значение равно TRUE, используется ImportTypes, в противном случае импорт должен выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="5673f-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="5673f-109">Флаги, передаваемые в [метод OpenScope](../metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="5673f-109">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="5673f-110">Получает идентификатор импортируемого файла.</span><span class="sxs-lookup"><span data-stu-id="5673f-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="5673f-111">Получает интерфейс [интерфейса IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) для области импорта сборки.</span><span class="sxs-lookup"><span data-stu-id="5673f-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="5673f-112">Имеет значение NULL, если файл не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="5673f-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="5673f-113">Получает число импортированных файлов и (или) областей.</span><span class="sxs-lookup"><span data-stu-id="5673f-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5673f-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5673f-114">Return Value</span></span>  
 <span data-ttu-id="5673f-115">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="5673f-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5673f-116">Требования</span><span class="sxs-lookup"><span data-stu-id="5673f-116">Requirements</span></span>  
 <span data-ttu-id="5673f-117">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="5673f-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5673f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5673f-118">See also</span></span>

- [<span data-ttu-id="5673f-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="5673f-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="5673f-120">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="5673f-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="5673f-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="5673f-121">ALink API</span></span>](index.md)
