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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3c6b9e1239dc1baed9428d4fe967eb8274a9304
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789809"
---
# <a name="getscope2-method"></a><span data-ttu-id="c2035-102">Метод GetScope2</span><span class="sxs-lookup"><span data-stu-id="c2035-102">GetScope2 Method</span></span>
<span data-ttu-id="c2035-103">Получает область импортирования.</span><span class="sxs-lookup"><span data-stu-id="c2035-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2035-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2035-104">Syntax</span></span>  
  
```  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="c2035-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2035-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c2035-106">Идентификатор целевой сборки.</span><span class="sxs-lookup"><span data-stu-id="c2035-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="c2035-107">Идентификатор файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="c2035-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="c2035-108">Отсчитываемый от нуля область для импорта.</span><span class="sxs-lookup"><span data-stu-id="c2035-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="c2035-109">Получает указатель на [интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) интерфейс для указанной области.</span><span class="sxs-lookup"><span data-stu-id="c2035-109">Receives pointer to [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2035-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c2035-110">Return Value</span></span>  
 <span data-ttu-id="c2035-111">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="c2035-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2035-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c2035-112">Requirements</span></span>  
 <span data-ttu-id="c2035-113">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="c2035-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2035-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c2035-114">See also</span></span>

- [<span data-ttu-id="c2035-115">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="c2035-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="c2035-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="c2035-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="c2035-117">API ALink</span><span class="sxs-lookup"><span data-stu-id="c2035-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
