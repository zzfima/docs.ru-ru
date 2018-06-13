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
ms.openlocfilehash: 77cd8b7d791d11f6d40386f4747c60cd4832521a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428098"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="4b6fc-102">Структура SYMLINEDELTA</span><span class="sxs-lookup"><span data-stu-id="4b6fc-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="4b6fc-103">Предоставляет сведения о методах, перемещенных в результате редактирования обработчика символов.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b6fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b6fc-104">Syntax</span></span>  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="4b6fc-105">Участники</span><span class="sxs-lookup"><span data-stu-id="4b6fc-105">Members</span></span>  
  
|<span data-ttu-id="4b6fc-106">Член</span><span class="sxs-lookup"><span data-stu-id="4b6fc-106">Member</span></span>|<span data-ttu-id="4b6fc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4b6fc-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="4b6fc-108">Токен метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="4b6fc-109">Число строк, что метод был перемещен.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4b6fc-110">Требования</span><span class="sxs-lookup"><span data-stu-id="4b6fc-110">Requirements</span></span>  
 <span data-ttu-id="4b6fc-111">**Заголовок:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="4b6fc-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b6fc-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4b6fc-112">See Also</span></span>  
 [<span data-ttu-id="4b6fc-113">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="4b6fc-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
