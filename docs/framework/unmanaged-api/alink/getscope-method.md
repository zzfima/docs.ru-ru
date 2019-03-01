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
ms.openlocfilehash: c5798fc488cf4453b6abcf00a7169b1ec0b529ec
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965375"
---
# <a name="getscope-method"></a><span data-ttu-id="d7513-102">Метод GetScope</span><span class="sxs-lookup"><span data-stu-id="d7513-102">GetScope Method</span></span>
<span data-ttu-id="d7513-103">Получает область импортирования.</span><span class="sxs-lookup"><span data-stu-id="d7513-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7513-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7513-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7513-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7513-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d7513-106">Уникальный идентификатор импортируемой сборки.</span><span class="sxs-lookup"><span data-stu-id="d7513-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d7513-107">Уникальный идентификатор файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="d7513-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="d7513-108">Отсчитываемый от нуля область для импорта.</span><span class="sxs-lookup"><span data-stu-id="d7513-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="d7513-109">Получает [интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейс для области.</span><span class="sxs-lookup"><span data-stu-id="d7513-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7513-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d7513-110">Return Value</span></span>  
 <span data-ttu-id="d7513-111">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="d7513-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7513-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d7513-112">Requirements</span></span>  
 <span data-ttu-id="d7513-113">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="d7513-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7513-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d7513-114">See also</span></span>
- [<span data-ttu-id="d7513-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="d7513-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="d7513-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="d7513-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="d7513-117">API ALink</span><span class="sxs-lookup"><span data-stu-id="d7513-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
