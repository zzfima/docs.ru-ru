---
title: Перечисление CorSymVarFlag
ms.date: 03/30/2017
api_name:
- CorSymVarFlag
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymVarFlag
helpviewer_keywords:
- CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5b387ee7fd4cc0088c90d2b8278fbf18bb36f51
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755679"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="c12e0-102">Перечисление CorSymVarFlag</span><span class="sxs-lookup"><span data-stu-id="c12e0-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="c12e0-103">Указывает, является ли переменная, созданная компилятором.</span><span class="sxs-lookup"><span data-stu-id="c12e0-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c12e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c12e0-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="c12e0-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c12e0-105">Members</span></span>  
  
|<span data-ttu-id="c12e0-106">Член</span><span class="sxs-lookup"><span data-stu-id="c12e0-106">Member</span></span>|<span data-ttu-id="c12e0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c12e0-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="c12e0-108">Указывает, что заданной переменной, созданный компилятором.</span><span class="sxs-lookup"><span data-stu-id="c12e0-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c12e0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c12e0-109">Requirements</span></span>  
 <span data-ttu-id="c12e0-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c12e0-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c12e0-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c12e0-111">See also</span></span>

- [<span data-ttu-id="c12e0-112">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="c12e0-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
