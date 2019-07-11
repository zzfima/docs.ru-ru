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
ms.openlocfilehash: d98ebed2eb853d5dc8177b0b044bf654c3978494
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744348"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="2a099-102">Структура SYMLINEDELTA</span><span class="sxs-lookup"><span data-stu-id="2a099-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="2a099-103">Содержит описание методов, которые были перемещены в результате изменения обработчику символов.</span><span class="sxs-lookup"><span data-stu-id="2a099-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a099-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a099-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="2a099-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2a099-105">Members</span></span>  
  
|<span data-ttu-id="2a099-106">Член</span><span class="sxs-lookup"><span data-stu-id="2a099-106">Member</span></span>|<span data-ttu-id="2a099-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2a099-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="2a099-108">Токен метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="2a099-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="2a099-109">Число строк, которые метод был перемещен.</span><span class="sxs-lookup"><span data-stu-id="2a099-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a099-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2a099-110">Requirements</span></span>  
 <span data-ttu-id="2a099-111">**Заголовок.** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="2a099-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a099-112">См. также</span><span class="sxs-lookup"><span data-stu-id="2a099-112">See also</span></span>

- [<span data-ttu-id="2a099-113">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="2a099-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
