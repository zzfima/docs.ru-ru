---
title: Метод PreCloseAssembly
ms.date: 03/30/2017
api_name:
- IALink.PreCloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- PreCloseAssembly
helpviewer_keywords:
- PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aab42e939651d75b1933962d72ba8bec1090f52d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184513"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="71098-102">Метод PreCloseAssembly</span><span class="sxs-lookup"><span data-stu-id="71098-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="71098-103">Закрывает файл сборки.</span><span class="sxs-lookup"><span data-stu-id="71098-103">Closes the assembly file.</span></span> <span data-ttu-id="71098-104">Этот метод следует вызывайте после закрытия всех файлов, но до закрытия файла сборки.</span><span class="sxs-lookup"><span data-stu-id="71098-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="71098-105">Не вызывайте этот метод для несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="71098-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71098-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71098-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="71098-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="71098-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="71098-108">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="71098-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71098-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="71098-109">Return Value</span></span>  
 <span data-ttu-id="71098-110">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="71098-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71098-111">Требования</span><span class="sxs-lookup"><span data-stu-id="71098-111">Requirements</span></span>  
 <span data-ttu-id="71098-112">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="71098-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71098-113">См. также</span><span class="sxs-lookup"><span data-stu-id="71098-113">See also</span></span>

- [<span data-ttu-id="71098-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="71098-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="71098-115">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="71098-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="71098-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="71098-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
