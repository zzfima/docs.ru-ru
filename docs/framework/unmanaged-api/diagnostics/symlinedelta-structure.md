---
title: Структура SYMLINEDELTA
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fabc8f77b12865d0d971b5934d7de27b52f3e813
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159488"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="ebcba-102">Структура SYMLINEDELTA</span><span class="sxs-lookup"><span data-stu-id="ebcba-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="ebcba-103">Содержит описание методов, которые были перемещены в результате изменения обработчику символов.</span><span class="sxs-lookup"><span data-stu-id="ebcba-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebcba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebcba-104">Syntax</span></span>  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="ebcba-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ebcba-105">Members</span></span>  
  
|<span data-ttu-id="ebcba-106">Член</span><span class="sxs-lookup"><span data-stu-id="ebcba-106">Member</span></span>|<span data-ttu-id="ebcba-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ebcba-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="ebcba-108">Токен метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="ebcba-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="ebcba-109">Число строк, которые метод был перемещен.</span><span class="sxs-lookup"><span data-stu-id="ebcba-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ebcba-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ebcba-110">Requirements</span></span>  
 <span data-ttu-id="ebcba-111">**Заголовок.** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="ebcba-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebcba-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ebcba-112">See also</span></span>

- [<span data-ttu-id="ebcba-113">Структуры хранения символов диагностики</span><span class="sxs-lookup"><span data-stu-id="ebcba-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
