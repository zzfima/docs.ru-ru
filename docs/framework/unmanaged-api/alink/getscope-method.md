---
title: Метод GetScope 1
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
ms.openlocfilehash: e2746073fbc6adfd7090aa9b3cc38e46c4411744
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400189"
---
# <a name="getscope-method1"></a><span data-ttu-id="56011-102">Метод GetScope 1</span><span class="sxs-lookup"><span data-stu-id="56011-102">GetScope Method1</span></span>
<span data-ttu-id="56011-103">Возвращает область импортирования.</span><span class="sxs-lookup"><span data-stu-id="56011-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56011-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56011-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56011-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="56011-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="56011-106">Уникальный идентификатор сборки для импорта.</span><span class="sxs-lookup"><span data-stu-id="56011-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="56011-107">Уникальный идентификатор файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="56011-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="56011-108">Отсчитываемый от нуля область для импорта.</span><span class="sxs-lookup"><span data-stu-id="56011-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="56011-109">Получает [IMetaDataImport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейс для области.</span><span class="sxs-lookup"><span data-stu-id="56011-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56011-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="56011-110">Return Value</span></span>  
 <span data-ttu-id="56011-111">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="56011-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56011-112">Требования</span><span class="sxs-lookup"><span data-stu-id="56011-112">Requirements</span></span>  
 <span data-ttu-id="56011-113">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="56011-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56011-114">См. также</span><span class="sxs-lookup"><span data-stu-id="56011-114">See Also</span></span>  
 [<span data-ttu-id="56011-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="56011-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="56011-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="56011-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="56011-117">API ALink</span><span class="sxs-lookup"><span data-stu-id="56011-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
