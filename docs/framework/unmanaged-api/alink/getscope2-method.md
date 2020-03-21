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
ms.openlocfilehash: 40df78cdf99c2e0f53be9664f3f5c6386b6c6f93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179394"
---
# <a name="getscope2-method"></a><span data-ttu-id="3a2eb-102">Метод GetScope2</span><span class="sxs-lookup"><span data-stu-id="3a2eb-102">GetScope2 Method</span></span>
<span data-ttu-id="3a2eb-103">Получает область импорта.</span><span class="sxs-lookup"><span data-stu-id="3a2eb-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a2eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a2eb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="3a2eb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3a2eb-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3a2eb-106">Идентификатор целевой сборки.</span><span class="sxs-lookup"><span data-stu-id="3a2eb-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3a2eb-107">Идентификатор файла, из которого импортировать.</span><span class="sxs-lookup"><span data-stu-id="3a2eb-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="3a2eb-108">Нулевой объем импорта.</span><span class="sxs-lookup"><span data-stu-id="3a2eb-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="3a2eb-109">Получает указатель на интерфейс [интерфейсi IMetaDataImport2](../metadata/imetadataimport2-interface.md) для указанного объема.</span><span class="sxs-lookup"><span data-stu-id="3a2eb-109">Receives pointer to [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a2eb-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3a2eb-110">Return Value</span></span>  
 <span data-ttu-id="3a2eb-111">Возвращает S_OK, если метод успешно.</span><span class="sxs-lookup"><span data-stu-id="3a2eb-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a2eb-112">Требования</span><span class="sxs-lookup"><span data-stu-id="3a2eb-112">Requirements</span></span>  
 <span data-ttu-id="3a2eb-113">Требуетa alink.h.</span><span class="sxs-lookup"><span data-stu-id="3a2eb-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a2eb-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3a2eb-114">See also</span></span>

- [<span data-ttu-id="3a2eb-115">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="3a2eb-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3a2eb-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="3a2eb-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3a2eb-117">API ALink</span><span class="sxs-lookup"><span data-stu-id="3a2eb-117">ALink API</span></span>](index.md)
