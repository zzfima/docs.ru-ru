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
ms.openlocfilehash: 0c797378f5e13f39c1c786237a3a7b9cf577fccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763654"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="7a1de-102">Перечисление CorSymVarFlag</span><span class="sxs-lookup"><span data-stu-id="7a1de-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="7a1de-103">Указывает, является ли переменная, созданная компилятором.</span><span class="sxs-lookup"><span data-stu-id="7a1de-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a1de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a1de-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="7a1de-105">Участники</span><span class="sxs-lookup"><span data-stu-id="7a1de-105">Members</span></span>  
  
|<span data-ttu-id="7a1de-106">Член</span><span class="sxs-lookup"><span data-stu-id="7a1de-106">Member</span></span>|<span data-ttu-id="7a1de-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7a1de-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="7a1de-108">Указывает, что заданной переменной, созданный компилятором.</span><span class="sxs-lookup"><span data-stu-id="7a1de-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7a1de-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7a1de-109">Requirements</span></span>  
 <span data-ttu-id="7a1de-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7a1de-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a1de-111">См. также</span><span class="sxs-lookup"><span data-stu-id="7a1de-111">See also</span></span>

- [<span data-ttu-id="7a1de-112">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="7a1de-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
