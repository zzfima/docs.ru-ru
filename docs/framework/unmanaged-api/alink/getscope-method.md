---
title: Метод1 GetScope
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
ms.openlocfilehash: 782697536f5e01fa29830a64e47d960a47fe4eae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663145"
---
# <a name="getscope-method1"></a><span data-ttu-id="6c67e-102">Метод1 GetScope</span><span class="sxs-lookup"><span data-stu-id="6c67e-102">GetScope Method1</span></span>
<span data-ttu-id="6c67e-103">Получает область импортирования.</span><span class="sxs-lookup"><span data-stu-id="6c67e-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c67e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c67e-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c67e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6c67e-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6c67e-106">Уникальный идентификатор импортируемой сборки.</span><span class="sxs-lookup"><span data-stu-id="6c67e-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="6c67e-107">Уникальный идентификатор файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="6c67e-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="6c67e-108">Отсчитываемый от нуля область для импорта.</span><span class="sxs-lookup"><span data-stu-id="6c67e-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="6c67e-109">Получает [интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейс для области.</span><span class="sxs-lookup"><span data-stu-id="6c67e-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c67e-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6c67e-110">Return Value</span></span>  
 <span data-ttu-id="6c67e-111">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="6c67e-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c67e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="6c67e-112">Requirements</span></span>  
 <span data-ttu-id="6c67e-113">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="6c67e-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c67e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6c67e-114">See also</span></span>
- [<span data-ttu-id="6c67e-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="6c67e-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="6c67e-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="6c67e-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="6c67e-117">API ALink</span><span class="sxs-lookup"><span data-stu-id="6c67e-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
