---
title: "Перечисление CorSymAddrKind"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 300913f9ea89044e425f9f05856d13fa15cdc015
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corsymaddrkind-enumeration"></a><span data-ttu-id="5e0ca-102">Перечисление CorSymAddrKind</span><span class="sxs-lookup"><span data-stu-id="5e0ca-102">CorSymAddrKind Enumeration</span></span>
<span data-ttu-id="5e0ca-103">Указывает тип адреса памяти.</span><span class="sxs-lookup"><span data-stu-id="5e0ca-103">Indicates the type of memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e0ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e0ca-104">Syntax</span></span>  
  
```  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a><span data-ttu-id="5e0ca-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5e0ca-105">Members</span></span>  
  
|<span data-ttu-id="5e0ca-106">Член</span><span class="sxs-lookup"><span data-stu-id="5e0ca-106">Member</span></span>|<span data-ttu-id="5e0ca-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="5e0ca-107">Description</span></span>|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|<span data-ttu-id="5e0ca-108">Указывает Microsoft промежуточного языка MSIL индекс локальной переменной или параметра.</span><span class="sxs-lookup"><span data-stu-id="5e0ca-108">Indicates a Microsoft intermediate language (MSIL) local variable or parameter index.</span></span>|  
|`ADDR_NATIVE_RVA`|<span data-ttu-id="5e0ca-109">Указывает относительный виртуальный адрес в модуль.</span><span class="sxs-lookup"><span data-stu-id="5e0ca-109">Indicates a relative virtual address into a module.</span></span>|  
|`ADDR_NATIVE_REGISTER`|<span data-ttu-id="5e0ca-110">Указывает регистр ЦП.</span><span class="sxs-lookup"><span data-stu-id="5e0ca-110">Indicates a CPU register.</span></span>|  
|`ADDR_NATIVE_REGREL`|<span data-ttu-id="5e0ca-111">Указывает, что первый адрес является регистром, а второй адрес — это смещение.</span><span class="sxs-lookup"><span data-stu-id="5e0ca-111">Indicates that the first address is a register and the second address is an offset.</span></span>|  
|`ADDR_NATIVE_OFFSET`|<span data-ttu-id="5e0ca-112">Указывает смещение от базового адреса.</span><span class="sxs-lookup"><span data-stu-id="5e0ca-112">Indicates an offset from a base address.</span></span>|  
|`ADDR_NATIVE_REGREG`|<span data-ttu-id="5e0ca-113">Указывает, что первый адрес является нижней частью регистра, а второй — верхней.</span><span class="sxs-lookup"><span data-stu-id="5e0ca-113">Indicates that the first address is the low portion of a register, and the second address is the high portion.</span></span>|  
|`ADDR_NATIVE_REGSTK`|<span data-ttu-id="5e0ca-114">Указывает, что первый адрес является нижней частью регистра и второй — верхней, а третий — это смещение.</span><span class="sxs-lookup"><span data-stu-id="5e0ca-114">Indicates that the first address is the low portion of a register, the second is the high portion, and the third is an offset.</span></span>|  
|`ADDR_NATIVE_STKREG`|<span data-ttu-id="5e0ca-115">Указывает, что первый адрес является регистром, второй — смещением и третий — верхней регистра.</span><span class="sxs-lookup"><span data-stu-id="5e0ca-115">Indicates that the first address is a register, the second is an offset, and the third is the high portion of the register.</span></span>|  
|`ADDR_BITFIELD`|<span data-ttu-id="5e0ca-116">Указывает, что первый адрес является началом поля, а второй — длина поля.</span><span class="sxs-lookup"><span data-stu-id="5e0ca-116">Indicates that the first address is the start of a field and the second address is the field length.</span></span>|  
|`ADDR_NATIVE_ISECTOFFSET`|<span data-ttu-id="5e0ca-117">Указывает, что первый адрес является разделом и второй адрес — это смещение.</span><span class="sxs-lookup"><span data-stu-id="5e0ca-117">Indicates that the first address is the section and the second address is an offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5e0ca-118">Требования</span><span class="sxs-lookup"><span data-stu-id="5e0ca-118">Requirements</span></span>  
 <span data-ttu-id="5e0ca-119">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5e0ca-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e0ca-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5e0ca-120">See Also</span></span>  
 [<span data-ttu-id="5e0ca-121">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="5e0ca-121">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
